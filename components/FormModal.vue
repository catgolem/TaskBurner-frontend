<template>
  <!-- 投稿フォーム全体 -->
  <div style="background: linear-gradient(-45deg, red, orange);" class="opacity-95w-full font-body h-full border-1 shadow-2xl px-16 pt-10 pb-8 rounded-2xl">
    <form @submit.prevent>
        <input style="margin-left: 3.2rem;" class="shadow-inner block px-6 py-1 my-3 rounded-2xl" placeholder="title" type="text" v-model="task.title">
        <input style="margin-left: 3.2rem;" class="shadow-inner block px-6 py-1 my-3 rounded-2xl ml-14" placeholder="description" type="text" v-model="task.description">
        <input style="margin-left: 3.2rem;" class="shadow-inner block px-6 py-1 my-3 rounded-2xl ml-14" placeholder="url" type="text" v-model="task.url"> 
        <input style="margin-left: 3.2rem;" class="shadow-inner block pl-6 pr-9 py-1 mt-3 rounded-2xl mb-6 ml-14" placeholder="deadline" type="datetime-local" v-model="task.deadline">
        <input type="radio" id="zero" value="0" v-model="task.level">
        <label class="px-1 font-semibold" for="zero">ぬるい</label>
        <input type="radio" id="one" value="1" v-model="task.level">
        <label class="px-1 font-semibold" for="one">温かい</label> 
        <input type="radio" id="two" value="2" v-model="task.level">
        <label class="px-1 font-semibold" for="two">ちょい熱</label>
        <input type="radio" id="three" value="3" v-model="task.level">
        <label class="px-1 font-semibold" for="three">熱い</label> 
        <input type="radio" id="four" value="4" v-model="task.level">
        <label class="px-1 font-semibold" for="four">激あつ</label>
      <button class="block hover:bg-white rounded-xl shadow-2xl ml-72 mt-3 align-bottom text-midle font-medium text-black opacity-80 border-b-3 text border-white px-2" type="submit" @click="posttask(); $emit('closeModal')">
        送信
      </button>
    </form>
  </div>
</template>

<script>
import axios from "~/plugin/axios.js";
export default {
  setup() {
  },
  data(){
    return {
      task: {
        title:'',
        description:'',
        level: 0,
        url:'',
        deadline:'',
      },
      show: false,
    }
  },
  methods: {
    async posttask(){
      var d = new Date(this.task.deadline);
      var yyyy = d.getFullYear() ;
      var MM = ('0' + (d.getMonth() + 1)).slice(-2);
      var dd = ('0' + d.getDate()).slice(-2);
      var hh = ('0' + d.getHours()).slice(-2);
      var mm = ('0' + d.getMinutes()).slice(-2);
      this.task.deadline = yyyy + '/' + MM + '/' + dd + ' ' + hh + ':' + mm;
      try {
        console.log("呼び出し成功");
        this.task.level = Number(this.task.level);
        const response = await axios.post('/api/v1/tasks',this.task, {
          headers:{ "jwt-token" : "Bearer " +  this.getToken }
        });
        console.log(response.data,"NewTask");
        this.$router.push('/SignIn');
      } catch (error) {
        console.error(error);
        console.error("postTaskでエラーが発生しました。");
        return;
      }
    },
  },
  computed: {
    getToken() {
      return this.$store.state.token;
    },
  }
}
</script>

