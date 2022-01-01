<template>
    <div style="background: linear-gradient(-45deg, red, pink); " class="w-screen h-screen  font-body relative">
      <div class="flex justify-center w-full mt-48 absolute text-shadow-sm align-middle text-2xl font-black opacity-80 shadow-inner pb-64 bg-white">
      </div>
      <div class="flex justify-center w-full mt-56 absolute text-shadow-sm align-middle text-2xl font-black opacity-80">
        <div class="opacity-80 mr-7 ml-3 pr-16 pl-10 border-b-3 border-black">
        <img class="inline-block shadow-3xl" src="../Assets/Fire2.png" alt="🔥">
        <div class="inline-block ml-2 text-shadow-sm align-middle text-2xl font-black text-red-600 ">
          Task Burner
        </div>
      </div>
      </div>
      <div class="z-20 flex justify-center w-full h-full absolute">
        <div class="flex items-center ">
          <div class="inline-block text-shadow-sm align-middle text-3xl font-black opacity-80">
            <nuxt-link to="/SignIn">
              <div class="inline-block">Sign In</div>
            </nuxt-link>
          </div>
          <div class="inline-block bg-gray-600 py-10 rounded-full px-0.5 mx-8 shadow-xl">
          </div>
          <div class="inline-block text-shadow-sm align-middle text-3xl font-black opacity-80">
            <nuxt-link to="/SignUp">
              <div class="inline-block">Sign Up</div>
            </nuxt-link>
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
