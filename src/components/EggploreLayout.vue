<template>
  <div class="eggplore-container">
    <eggplore-header/>
    <eggplore-content-one/>
    <eggplore-content-two/>
  </div>
</template>
<script>
import EggploreHeader from '../views/EggploreHeader.vue'
import EggploreContentOne from '@/views/EggploreContentOne.vue';
import EggploreContentTwo from '@/views/EggploreContentTwo.vue';
export default {
  name: "eggplore-app",
  components:{
    EggploreHeader,
    EggploreContentOne,
    EggploreContentTwo
  },
  data() {
    return {
      
    };
  },
};
</script>
<style>
body {
  margin: 0;
  padding: 0;
}
.eggplore-container {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  background: #FCFCFC;
  padding-bottom: 25px;
}


</style>
