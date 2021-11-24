<template>
  <div class="bg-gray-900 text-gray-200 py-5">
    <div class="container flex place-content-between text-lg uppercase">
      <div class="">Brand</div>
      <div class="">
        <router-link class="px-5 py-3 hover:bg-gray-700 transition duration-300" to="/">Home</router-link>
        <router-link class="px-5 py-3 hover:bg-gray-700 transition duration-300"  :to="{ name: 'About' }">About</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>
