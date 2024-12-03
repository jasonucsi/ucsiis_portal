<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/banner.png">
    <Landing/>
  </div>
</template>

<script>
import Landing from './components/Landing.vue'
import '@fortawesome/fontawesome-free/css/all.css';

export default {
  name: 'App',
  components: {
    Landing
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
  margin-top: 10px;
}
</style>