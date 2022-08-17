<template>
    <div class="second-box-container">
        <h5>Checkbox Second</h5>
        <div class="second-box-content">
            <div class="second-box-wrapper" v-for="(province, idx) in provinces_box" :key="idx" ref="boxWrapper">
                <input type="checkbox" v-model="selected_provinces" :value="province" :disabled="province.disabled" :ref="`checkProvince${province.value}`">
                <label for="checkbox">{{province.name}}</label>
            </div>
            <input type="checkbox" @change="setAll" >
            <label for="checkbox">All</label>
        </div>
    </div>
</template>
<script>


export default {
    name: 'second-checkbox',
    data(){
        return{
            provinces_box: [
                {name: 'Andijon', value: 'And'},
                {name: 'Buxoro', value: 'Bux'},
                {name: 'Farg\'ona', value: 'Far'},
                {name: 'Jizzax', value: 'Jiz'},
                {name: 'Namangan', value: 'Nam'},
                {name: 'Navoiy', value: 'Nav'},
                {name: 'Qashqadaryo', value: 'Qash'},
                {name: 'Samarqand', value: 'Sam'},
                {name: 'Sirdaryo', value: 'Sir'},
                {name: 'Surxondaryo', value: 'Sur'},
                {name: 'Toshkent', value: 'Tosh'},
                {name: 'Xorazm', value: 'Xor'},
                {name: 'Toshkent Shahar', value: 'G\'ij', disabled:true}
            ],
            selected_provinces: []
        }
    },
    props:{
        provinces: {
            type: Array,
            default: ()=> []
        }
    },
    methods:{
        checkSelected(e){
            console.log(e)
        },
        setAll() {
            if (this.selected_provinces.length === 0) {
                this.selected_provinces = this.provinces_box;
                // TODO: add class to the checkbox for interface
                // this.setAllClass()
                
            }
            
            else {
                this.selected_provinces = [];
                // TODO: remove class from the checkbox for interface
                // this.deleteAllClass()
            }
        },



      
    },
    watch: {
        'selected_provinces' : function(val){
            this.checkSelected(val)
        }
    }
}
</script>