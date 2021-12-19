<template>
  <!-- Task -->
  <div class="pb-2 pt-2 my-1 flex justify-start border-gray-00 border-b-4 border-dotted">
    <!-- 左 -->
    <div class="inline-block border-r-4 border-gray-600 pr-2">
      <div>
        {{deadline_date}}
      </div>
      <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
      <div class="inline-block ml-1">
        {{deadline_time}}
      </div>
    </div> 
    <!-- 右 -->
    <div class="inline-brock">
      <div class="ml-5">
        {{title}}
      </div>
      <div v-if="level == 0" class="ml-3 inline-block rounded-full px-1 border-4 border-red-200 align-middle">ぬるい</div>
      <div v-if="level == 1" class="ml-3 inline-block rounded-full px-1 border-4 border-red-400 align-middle">温かい</div>
      <div v-if="level == 2" class="ml-3 inline-block rounded-full px-1 border-4 border-red-500 align-middle">ちょい熱</div>
      <div v-if="level == 3" class="ml-3 inline-block rounded-full px-1 border-4 border-red-700 align-middle">熱い</div>
      <div v-if="level == 4" class="ml-3 inline-block rounded-full px-1 border-4 border-red-900 align-middle">激あつ</div>
      
      <button @click="compTask()">
        <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
      </button>
      <button @click="deleteTask()">
        <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
      </button>
      <a class="inline-block align-middle ml-1" target="_blank" :href="url">
        <img src="../Assets/link.png" alt="Url">
      </a>
    </div>
  </div>
</template>

<script>
import axios from "~/plugin/axios.js";
export default {
  props: [
    'id',
    'deadline_date',
    'deadline_time',
    'title',
    'level',
    'url',
  ],
  computed: {
    getToken() {
      return this.$store.state.token;
    }
  },
  methods: {
    async deleteTask(){
      try{
        console.log("deleteだよ！");
        const response_delete = await axios.delete('/api/v1/tasks/'+ this.id,{
          headers:{ "jwt-token" : "Bearer " +  this.getToken}
        });
        console.log(response_delete);
        this.$router.push('/SignIn');
        return;
      }catch (error) {
        console.error(error);
        console.error("deleteTaskでエラーが発生しました。");
        return;
      }
    },
    async compTask(){
      try{
        console.log("compだよ！");
        const response_comp = await axios.patch('/api/v1/tasks/complete/'+ this.id, this.id,{
          headers:{ "jwt-token" : "Bearer " +  this.getToken}
        });
        console.log(response_comp);
        this.$router.push('/SignIn');
        return;
      }catch (error) {
        console.error(error);
        console.error("compでエラーが発生しました。");
        return;
      }
    }
  },
}
</script>

<style>

</style>