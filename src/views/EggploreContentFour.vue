<template>
    <div class="other-components-container">
        <h4>Other Components</h4>
        <div class="other-components-content">
            <hr>
            <div class="components-wrapper">
                <eggplore-check-boxes/>
                <eggplore-radio-button/>
                <eggplore-selector/>
                <eggplore-tags/>
            </div>
        </div>
    </div>
</template>
<script>
import EggploreCheckBoxes from './eggplore-four/EggploreCheckBoxes.vue';
import EggploreRadioButton from './eggplore-four/EggploreRadioButton.vue';
import EggploreSelector from './eggplore-four/EggploreSelector.vue';
import EggploreTags from './eggplore-four/EggploreTags.vue';
export default {
    name: 'eggplore-content-four',
    components:{EggploreCheckBoxes, EggploreRadioButton, EggploreSelector, EggploreTags}
}
</script>