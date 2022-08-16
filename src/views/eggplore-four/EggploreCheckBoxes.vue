<template>
    <div class="checkboxes-container">
        <h5>CheckBoxes</h5>
        <div class="checkbox-content">
            <input type="checkbox" v-model="sport" @change="checkHobbie" :class="sport ? 'sport-active' : 'sport-deactive'">
            <input type="checkbox" v-model="travel" @change="checkHobbie" :class="travel ? 'travel-active' : 'travel-deactive'">
            <input type="checkbox" disabled>
            <input type="checkbox" :class="isChecked ? 'checkbox-checked' : 'checkbox-unchecked'">
        </div>
    </div>
</template>
<script>
export default {
    name: 'eggplore-checkboxes',
    data(){
        return{
            sport: false,
            travel: false,
            isChecked: false
        }
    },
    methods:{
        checkHobbie(){
            if(this.sport ==true && this.travel == true){
                this.isChecked = true
            }else if(this.sport == true && this){
                this.isChecked = false
            }
        }
    }
}
</script>