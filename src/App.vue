<template>
  <div id="app">
    <LvlProgression variant="line-outline" :total=100 :current=45 />
    <LvlUp variant="line-outline" title='C le titre' text='C le text'/>
  </div>
</template>

<script>
import LvlProgression from './components/LvlProgression.vue'
import LvlUp from './components/LvlUp.vue'

export default {
  name: 'app',
  components: {
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
