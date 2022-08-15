<template>
    <div class="selector-container">
        <h5>Selector</h5>
        <div class="selector-content">
            <input type="checkbox" value="male" v-model="male">
            <input type="checkbox" value="female" v-model="female">
        </div>
    </div>
</template>
<script>
export default {
    name: 'eggplore-selector',
    data(){
        return{
            male: false,
            female: false
        }
    }
}
</script>