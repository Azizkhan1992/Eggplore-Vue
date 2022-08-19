<template>
  <div class="eggplore-container">
    <eggplore-header/>
    <eggplore-content-one/>
    <eggplore-content-two/>
    <eggplore-content-three/>
    <eggplore-content-four/>
    <eggplore-content-five/>
    <eggplore-content-six/>
    <eggplore-content-eight/>
  </div>
</template>
<script>
import EggploreHeader from '../views/EggploreHeader.vue'
import EggploreContentOne from '@/views/EggploreContentOne.vue';
import EggploreContentTwo from '@/views/EggploreContentTwo.vue';
import EggploreContentThree from '@/views/EggploreContentThree.vue';
import EggploreContentFour from '@/views/EggploreContentFour.vue';
import EggploreContentFive from '@/views/EggploreContentFive.vue';
import EggploreContentSix from '@/views/EggploreContentSix.vue';
import EggploreContentEight from '@/views/EggploreContentEight.vue';
export default {
  name: "eggplore-app",
  components:{
    EggploreHeader,
    EggploreContentOne,
    EggploreContentTwo,
    EggploreContentThree,
    EggploreContentFour,
    EggploreContentFive,
    EggploreContentSix,
    EggploreContentEight
  },
  data() {
    return {
      count: 5
    };
  },
  watch: {
    'count': function (val) {
      console.log('count', val)
    }
  }
};
</script>
<style>


</style>
