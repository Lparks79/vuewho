<template>
  <div id="app">
    <img alt="Vue logo" class="logo" src="./assets/logo.jpg">
    <PartsForm msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import PartsForm from './components/PartsForm.vue'

export default {
  name: 'app',
  components: {
    PartsForm
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.logo {
  width: 30%;
}
</style>
