<template>
  <div id="app">
    <img src="./assets/would-you-rather-9.jpg" alt="Would you rather logo">
    <would-you-rather />
  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 15px;
}
img {
  max-width: 90%;
  max-height: 90%;
}
</style>
