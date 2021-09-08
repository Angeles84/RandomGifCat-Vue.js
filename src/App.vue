<template>
  <div id="app" class="mt-3 mt-md-5">
    <RandomGifCat encabezado="Random Gif Cat"/>
  </div>
</template>

<script>
import RandomGifCat from './components/RandomGifCat.vue'

export default {
  name: 'App',
  components: {
    RandomGifCat
  }
}
</script>

<style>
body {
  background-color: lightblue;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
