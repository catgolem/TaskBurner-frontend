<template>
  <div>
    <div style="background: linear-gradient(-45deg, red, pink); " class="w-screen h-screen  font-body relative">
      <div class="flex justify-center w-full h-full absolute">
        <div class="flex items-center ">
          <form @submit.prevent>
            <input class="block my-3 py-2 px-1 pl-3 rounded-full shadow-inner" type="text" required placeholder="name" v-model="user.name"> 
            <input class="block my-3 py-2 px-1 pl-3 rounded-full shadow-inner" type="text" required placeholder="email" v-model="user.email"> 
            <input class="block my-3 py-2 px-1 pl-3 rounded-full shadow-inner" type="password" required placeholder="password" v-model="user.password">             
            <button class="border-b-3 px-3 block ml-40 text-shadow-sm align-middle text-base font-medium opacity-80 hover:bg-white shadow-2xl rounded-xl" type="submit" @click="postuser">
              送信
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "~/plugin/axios.js";
export default {
  setup() {
  },
  data(){
    return {
      user: {
        name: '',
        email:'',
        password:'',
      }
    }
  },
  methods: {
    async postuser(){
      try {
        const response = await axios.post('/api/v1/users/signup',this.user);
      } catch (error) {
        console.error(error);
        console.error("SignUpでエラーが発生しました。");
        return;
      }
      try {
        const response_signin = await axios.post('/api/v1/users/signin',{
          email:this.user.email,
          password:this.user.password
          });
        this.$store.commit("setIsLogin", true);
        this.$store.commit("setToken", response_signin.data.jwt);
        localStorage.setItem("jwt", response_signin.data.jwt);
        this.$router.push('/Home');
      } catch (error) {
        console.error(error);
        console.error("SignInでエラーが発生しました。");
        return;
      }
    },
  }
}
</script>