<template>
  <!-- Rank -->
  <div class="pb-2 pt-2 my-1 flex justify-start border-gray-00 border-b-4 border-dotted">
    <!-- 左 -->
    <div class="flex justify-start border-r-4 border-gray-600 pr-2">
      <div v-if="number == 1" class="pt-4">
        <img class="inline-block" src="../Assets/champ.png">
        <h1 class="inline-block">
          No.1
        </h1>
      </div>

      <div v-if="number == 2" class="pt-4">
        <img class="inline-block" src="../Assets/rank.png">
        <h1 class="inline-block">
          No.2
        </h1>
      </div>

      <div v-if="number == 3" class="pt-4">
        <img class="inline-block" src="../Assets/rank.png">
        <h1 class="inline-block">
          No.3
        </h1>
      </div>

      <div v-if="number == 4" class="pt-4">
        <img class="inline-block" src="../Assets/Fire2.png">
        <h1 class="inline-block">
          No.4
        </h1>
      </div>

      <div v-if="number == 5" class="pt-4">
        <img class="inline-block" src="../Assets/Fire2.png">
        <h1 class="inline-block">
          No.5
        </h1>
      </div>
    </div> 

    <!-- 右 -->
    <div class="inline-brock">
      <div v-if="number == 1" class="ml-3">
        You're the Crazyest Burner in the world!!!
      </div>
      <div v-if="number == 2" class="ml-3">
        You can be the sun!!
      </div>
      <div v-if="number == 3" class="ml-3">
        You are the hottest man in the world!
      </div>
      <div v-if="number == 4" class="ml-3">
        I'll melt in your heat!
      </div>
      <div v-if="number == 5" class="ml-3">
        Wow, the fish burned because of you!
      </div>

      <img class="inline-block ml-1 pl-3" src="../Assets/per.png" alt="完了">
      <div class="ml-3 inline-block rounded-full align-middle">{{name}}</div>    
      <div class="inline-block mr-14 pl-4 pr-6 ">
        <img class="inline-block" src="../Assets/Themo2.png" alt="温度計">
          <div class="inline-block text-shadow-sm align-middle ml-1 text-2xl text-red-600 font-black">
            {{temperature}}°C
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props:[
    `id`,
    'name',
    `temperature`,
    'number'
  ]

}
</script>

<style>

</style>