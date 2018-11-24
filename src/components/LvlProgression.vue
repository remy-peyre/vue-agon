<template>
  <div>
    lvl progression
    <h5>le test style in js</h5>
  </div>
</template>

<script>
import styled from 'vue-styled-components';

const LvlProgression = styled.h5`
  font-size: 2.5em;
  text-align: center;
  color: palevioletred;
`;
export default {
  name: 'LvlProgression',
  props: {
    //msg: String
  }
  
}
</script>



<style scoped>



</style>
