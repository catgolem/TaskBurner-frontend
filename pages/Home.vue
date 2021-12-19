<template>
  <div style="background: linear-gradient(-45deg, red, orange);" class="h-screen font-body z-10">
    <div style="left: calc(50vw - 252.1px); top: calc(50vh - 170px);" class="z-30 absolute">
      <form-modal class=" " @closeModal="show=false" v-if="show">
      </form-modal>
    </div>

    <!-- モーダル時のOpacity -->
    <div class="opacity-40 absolute bg-white z-20 w-full h-full" v-if="show">
    </div>

    <!-- 一番上のブロック -->
    <div class="flex justify-between pt-8 pl-10 pb-5">
      <!-- TaskBurner -->
      <div class="border-b-3 border-black pl-1 pr-4 ml-2 opacity-80">
        <img class="inline-block shadow-2xl" src="../Assets/Fire2.png" alt="🔥">
        <div class="inline-block text-shadow-sm align-middle ml-1 text-2xl font-black text-red-600 ">
          Task Burner
        </div>
      </div>
      <!-- 温度計 -->
      <div class="border-3 rounded-full bg-white border-black mr-14 pl-4 pr-6 opacity-80 shadow-md">
        <img class="inline-block" src="../Assets/Themo2.png" alt="温度計">
        <div class="inline-block text-shadow-sm align-middle ml-1 text-2xl text-red-600 font-black">
          {{temp}}°C
        </div>
      </div>
    </div>

    <!-- メインのブロック -->
    <div style="height: 86vh;" class="grid grid-rows-3 grid-cols-2 gap-7 py-8 mx-10 opacity-80">

      <!-- 左のブロック（タスク一覧） -->
      <div class="border-4 border-black row-span-3 col-span-1 shadow-lg rounded-lg overflow-hidden bg-gray-100">
        <!-- タイトル -->
        <div class="border-b-4 border-black flex justify-start text-shadow-sm align-middle ml-3 text-2xl font-black py-2">
          <img class="mr-2" src="../Assets/TaskIcon2.png" alt="リストアイコン">
          <div>Task List</div>
          <button class="ml-auto flex justify-start" @click="show=true">
            <img class="mr-3" src="../Assets/add.png" alt="追加">
            <div class="mr-6 text-shadow-sm align-middle text-2xl font-black">Add</div>
          </button>
        </div>
        <!-- リスト -->        
        <div style="height: 68vh;" class="overscroll-auto overflow-auto pl-4 text-2xl font-black opacity-80 section">
          <task-list v-for="undone_task in undone_tasks" :key="undone_task.id" :id="undone_task.id" :deadline_date="undone_task.deadline_date" :deadline_time="undone_task.deadline_time" :url="undone_task.url" :level="undone_task.level" :title="undone_task.title"/>
        </div>
      </div>


      <!-- 右側のブロック（Doneの部分） -->
      <div class="row-span-1 col-span-1 border-4 border-black shadow-lg rounded-lg overflow-hidden bg-gray-100">
        <!-- タイトル -->
        <div class="border-b-4 border-black flex justify-start text-shadow-sm align-middle ml-3 text-2xl font-black py-2">
          <img class="mr-2" src="../Assets/TaskIcon2.png" alt="リストアイコン">
          Done Task
        </div>
        <!-- リスト -->
        <div style="height: 14vh;" class="overscroll-auto overflow-auto pl-4 text-2xl font-black opacity-80 section">
          <done-list v-for="done_task in done_tasks" :key="done_task.id" :id="done_task.id" :deadline_date="done_task.deadline_date" :deadline_time="done_task.deadline_time" :url="done_task.url" :level="done_task.level" :title="done_task.title"/>
        </div>
      </div>


      <!-- 右側のブロック（ランキングのところ） -->
      <div class="row-span-2 col-span-1 border-4 border-black shadow-lg rounded-lg bg-red-300 overflow-hidden">
        <!-- タイトル -->
        <div class="border-b-4 border-black flex justify-start text-shadow-sm align-middle ml-3 text-2xl font-black py-2">
          <img class="mr-2" src="../Assets/TaskIcon2.png" alt="リストアイコン">
          Crazy Burners !!
        </div>
        <!-- リスト -->
        <div style="height: 41vh;" class="overscroll-auto overflow-auto align-middle text-2xl font-black pl-4 opacity-80 section">
          <ranking/>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
import axios from "~/plugin/axios.js";
import DoneList from '../components/DoneList.vue'
import FormModal from '../components/FormModal.vue'
import Ranking from '../components/Ranking.vue';
export default {
  components: { 
    FormModal,
    DoneList,
    Ranking 
  },
  data () {
    return {
      show: false,
      temp:0,
      undone_tasks:[],
      done_tasks:[],
    }
  },
  computed: {
    getToken() {
      return this.$store.state.token;
    }
  },
  methods: {
    async getTasks(){
      try {
        console.log("できた");
        console.log(this.getToken);
        const response = await axios.get('/api/v1/tasks',{
          headers:{ "jwt-token" : "Bearer " +  this.getToken}
        });
        console.log(response);
        this.undone_tasks = response.data.uncompleted;
        this.done_tasks = response.data.completed;

        this.undone_tasks = this.undone_tasks.map(
         (undone_task) => {
            var d = new Date(undone_task.deadline);
            var yyyy = d.getFullYear();
            var MM = ('0' + (d.getMonth() + 1)).slice(-2);
            var dd = ('0' + d.getDate()).slice(-2);
            var hh = ('0' + d.getHours()).slice(-2);
            var mm = ('0' + d.getMinutes()).slice(-2);
            undone_task.deadline = yyyy + '/' + MM + '/' + dd + ' ' + hh + ':' + mm;
            undone_task.deadline_date = yyyy + '/' + MM + '/' + dd;
            undone_task.deadline_time = hh + ':' + mm;
            return undone_task;
         } 
        );
        this.done_tasks = this.done_tasks.map(
         (done_task) => {
            var d = new Date(done_task.deadline);
            var yyyy = d.getFullYear();
            var MM = ('0' + (d.getMonth() + 1)).slice(-2);
            var dd = ('0' + d.getDate()).slice(-2);
            var hh = ('0' + d.getHours()).slice(-2);
            var mm = ('0' + d.getMinutes()).slice(-2);
            done_task.deadline = yyyy + '/' + MM + '/' + dd + ' ' + hh + ':' + mm;
            done_task.deadline_date = yyyy + '/' + MM + '/' + dd;
            done_task.deadline_time = hh + ':' + mm;
            return done_task;
         } 
        );
        console.log(this.undone_tasks);
        return;
      } catch (error) {
        console.error(error);
        console.error("getTaskでエラーが発生しました。");
        return;
      }
    },
    async getTemp(){
      try {
        const response_temp = await axios.get('/api/v1/users/me',{
            headers:{ "jwt-token" : "Bearer " +  this.getToken}
          });
        console.log(response_temp.data);
        this.temp = response_temp.data.temperature;
        return;
      } catch (error) {
        console.error(error);
        console.error("getTmpでエラーが発生しました。");
        return;
      }
    },
  },
  async mounted(){
      await this.getTasks()
      console.log("コンソールだよ");
      await this.getTemp()
      console.log("てんぷだよ");
  },
}
</script>

<style scoped>

  .section::-webkit-scrollbar {
    width: 16px;
  }
  .section::-webkit-scrollbar-track {
    background-color: #e4e4e4;
    border-radius: 100px;
  }
  .section::-webkit-scrollbar-thumb {
    background-color: #d4aa70;
    border-radius: 100px;
  }
</style>