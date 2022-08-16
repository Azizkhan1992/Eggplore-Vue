<template>
    <div class="eggplore-five-container">
        <div class="eggplore-five-content">
            <eggplore-slider/>
            <eggplore-tab-bar/>
        </div>
    </div>
</template>
<script>
import EggploreSlider from './eggplore-five/EggploreSlider.vue';
import EggploreTabBar from './eggplore-five/EggploreTabBar.vue';
export default {
    name: 'eggplore-five',
    components:{EggploreSlider, EggploreTabBar}
}
</script>