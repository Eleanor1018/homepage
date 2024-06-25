<script setup>
  import Homepage from "@/components/Homepage.vue";
</script>

<template>
  <div id="app">
    <Homepage></Homepage>
<!--    <router-view v-if="isRouterAlive"></router-view>-->
  </div>
</template>

<style scoped>
  #app{
    width: 100vw;
    height: 100vh;
  }
</style>
