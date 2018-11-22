<template>
  <div id="app">
    <FirstCompo msg="Le test mon Bro"/>
  </div>
</template>

<script>
import FirstCompo from './components/FirstCompo.vue'

export default {
  name: 'app',
  components: {
    FirstCompo
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
</style>
