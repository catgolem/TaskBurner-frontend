<template>
  <div style="background-color: #feebc8;">
    <!-- 一番上のブロック -->
    <div style="background-color: #feebc8;" class="flex justify-between pt-8 pl-10 pb-8">
      <!-- TaskBurner -->
      <div class="border-b-3 border-black pl-1 pr-4 opacity-80">
        <img class="inline-block shadow-2xl" src="../Assets/Fire2.png" alt="🔥">
        <div class="inline-block text-shadow-sm align-middle ml-1 text-2xl font-black">
          Task Burner
        </div>
      </div>
      <!-- 温度計 -->
      <div class="border-3 rounded-full border-black mr-14 pl-4 pr-6 opacity-80 shadow-md">
        <img class="inline-block" src="../Assets/Themo2.png" alt="温度計">
        <div class="inline-block text-shadow-sm align-middle ml-1 text-2xl text-red-600 font-black">
          200°C
        </div>
      </div>
    </div>

    <!-- メインのブロック -->
    <div class="grid grid-rows-3 grid-cols-2 gap-6 h-screen py-8 mx-10 ">
      <!-- 左のブロック（タスク一覧） -->
      <div class="border-4 row-span-3 col-span-1 shadow-lg rounded-lg">
        <!-- タイトル -->
        <div class="border-4 flex justify-start opacity-80 text-shadow-sm align-middle ml-1 text-2xl font-black">
          <img class="mr-2" src="../Assets/TaskIcon2.png" alt="リストアイコン">
          Task List
        </div>
      </div>

      <!-- 右側のブロック（ランキング部分） -->
      <div class="row-span-1 col-span-1 border-2 shadow-lg rounded-lg">
        <div class="">
        </div>
      </div>

      <!-- 右側のブロック（完了一覧） -->
      <div class="row-span-2 col-span-1 border-6 shadow-lg rounded-lg">
        <div class="">
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>