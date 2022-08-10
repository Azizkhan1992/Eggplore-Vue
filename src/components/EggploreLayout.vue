<template>
  <div class="eggplore-container">
    <eggplore-header/>
    <eggplore-content-one/>
  </div>
</template>
<script>
import EggploreHeader from '../views/EggploreHeader.vue'
import EggploreContentOne from '@/views/EggploreContentOne.vue';
export default {
  name: "eggplore-app",
  components:{
    EggploreHeader,
    EggploreContentOne
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
  display: flex;
  flex-direction: column;
}


</style>
