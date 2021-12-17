<template>
  <div style="background: linear-gradient(-45deg, orange, pink);" class="h-screen font-body">
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
      <div class="border-3 rounded-full border-black mr-14 pl-4 pr-6 opacity-80 shadow-md">
        <img class="inline-block" src="../Assets/Themo2.png" alt="温度計">
        <div class="inline-block text-shadow-sm align-middle ml-1 text-2xl text-red-600 font-black">
          200°C
        </div>
      </div>
    </div>

    <!-- メインのブロック -->
    <div style="height: 90vh;" class="grid grid-rows-3 grid-cols-2 gap-7 py-8 mx-10 opacity-80">
      <!-- 左のブロック（タスク一覧） -->
      <div class="border-4 border-black row-span-3 col-span-1 shadow-lg rounded-lg overflow-hidden">
        <!-- タイトル -->
        <div class="border-b-4 border-black flex justify-start text-shadow-sm align-middle ml-3 text-2xl font-black py-2">
          <img class="mr-2" src="../Assets/TaskIcon2.png" alt="リストアイコン">
          <div>Task List</div>
          <img class="ml-auto mr-3" src="../Assets/add.png" alt="追加">
          <div class="mr-6">Add</div>
        </div>
        <!-- リスト -->
        <div style="height: 76.8vh;" class="overscroll-auto overflow-auto pl-4 text-2xl font-black opacity-80 section">
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/comp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
        </div>
      </div>


      <!-- 右側のブロック（Doneの部分） -->
      <div class="row-span-1 col-span-1 border-4 border-black shadow-lg rounded-lg overflow-hidden">
        <!-- タイトル -->
        <div class="border-b-4 border-black flex justify-start text-shadow-sm align-middle ml-3 text-2xl font-black py-2">
          <img class="mr-2" src="../Assets/TaskIcon2.png" alt="リストアイコン">
          Done Task
        </div>
        <!-- リスト -->
        <div style="height: 19vh;" class="overscroll-auto overflow-auto pl-4 text-2xl font-black opacity-80 section">
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/uncomp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/uncomp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>
          <!-- Task -->
          <div class="pb-2 pt-2 my-1 inline-block flex justify-start border-gray-00 border-b-4 border-dotted">
            <!-- 左 -->
            <div class="inline-block border-r-4 border-gray-600 pr-2">
              <div>
                2021/12/20
              </div>
              <img class="inline-block" src="../Assets/deadline.png" alt="締め切り">
              <div class="inline-block ml-1">
                17:00
              </div>
            </div> 
            <!-- 右 -->
            <div class="inline-brock">
              <div class="ml-3">
                ねこちゃんをナデナデするぅぅの
              </div>
              <div class="ml-3 inline-block rounded-full px-1 border-3 border-red-700 align-middle">激熱</div>
              <img class="inline-block ml-1" src="../Assets/uncomp.png" alt="完了">
              <img class="inline-block ml-1" src="../Assets/delete.png" alt="削除">
              <a class="inline-block align-middle ml-1" href="https://google.com">
                <img src="../Assets/link.png" alt="Url">
              </a>
            </div>
          </div>

        </div>
      </div>

      <!-- 右側のブロック（ランキングのところ） -->
      <div class="row-span-2 col-span-1 border-4 border-black shadow-lg rounded-lg">
        <!-- タイトル -->
        <div class="border-b-4 border-black flex justify-start text-shadow-sm align-middle ml-3 text-2xl font-black py-2">
          <img class="mr-2" src="../Assets/TaskIcon2.png" alt="リストアイコン">
          Crazy Burners !!
        </div>
      </div>
      <!-- リスト -->
      <div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
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