<template>
  <div>
    <!-- 投稿フォーム全体 -->
    <div>
     <form @submit.prevent>
      <input class="border-2 block" type="text" v-model="task.name">
      <input class="border-2 block" type="text" v-model="user.email"> 
      <input class="border-2 block" type="text" v-model="user.password"> 
      <button class="border-2 block" type="submit" @click="postuser">
        送信
      </button>
    </form>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>