<template>
  <div id="app">
    <FirstCompo msg="Le test mon Bro"/>
    <LvlProgression/>
    <LvlUp/>
  </div>
</template>

<script>
import FirstCompo from './components/FirstCompo.vue'
import LvlProgression from './components/LvlProgression.vue'
import LvlUp from './components/LvlUp.vue'
//import styled from 'vue-styled-components';

export default {
  name: 'app',
  components: {
    FirstCompo,
    LvlProgression,
    LvlUp
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
