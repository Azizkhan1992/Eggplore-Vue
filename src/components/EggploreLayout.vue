<template>
  <div class="eggplore-container">
    <eggplore-header/>
    <eggplore-content-one/>
    <eggplore-content-two/>
    <eggplore-content-three/>
  </div>
</template>
<script>
import EggploreHeader from '../views/EggploreHeader.vue'
import EggploreContentOne from '@/views/EggploreContentOne.vue';
import EggploreContentTwo from '@/views/EggploreContentTwo.vue';
import EggploreContentThree from '@/views/EggploreContentThree.vue';
export default {
  name: "eggplore-app",
  components:{
    EggploreHeader,
    EggploreContentOne,
    EggploreContentTwo,
    EggploreContentThree
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
  min-height: 100vh;
  height: auto;
  display: flex;
  flex-direction: column;
  background: #FCFCFC;
  padding-bottom: 25px;
}

@font-face{
  font-family: 'SF Pro Text';
  src: url(@/assets/font/FontsFree-Net-SFProText-Regular.ttf);
}

</style>
