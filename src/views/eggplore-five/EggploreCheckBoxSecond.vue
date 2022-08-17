<template>
    <div class="second-box-container">
        <h5>Checkbox Second</h5>
        <div class="second-box-content">
            <div class="second-box-wrapper" v-for="(province, idx) in provinces_box" :key="idx" ref="boxWrapper">
                <input type="checkbox" :value="province.value" :disabled="province.disabled" @change="setEvent(province.value)" ref="checkProvince">
                <label for="checkbox">{{province.name}}</label>
            </div>
            
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
                {name: 'Toshkent Shahar', value: 'G\'ij', disabled:true},
                {name: 'All', value: 'All'}
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
    mounted(){
        this.getParent()
    },
    computed:{
        
    },
    methods:{
        setEvent(k){
            const inp_elem = this.$refs.checkProvince
            let check_inp_elem
            inp_elem.forEach(elem => {
                check_inp_elem = elem.checked
                // console.log(check_inp_elem)
            })
            if(k == 'All'){
                this.selected_provinces = this.provinces_box
                if(check_inp_elem && this.selected_provinces == this.provinces_box){
                    this.setAllClass(inp_elem)
                }
                else{
                    this.deleteAllClass(inp_elem)
                }
                
            }
            
            else{
                let selected = this.provinces_box.find(elem => elem.value == k)
                console.log(selected)
            }
                // console.log(inp_elem)
        },
        setAllClass(e){
                e.forEach(item =>{
                item.classList.add('all-checkbox-active')
            })
        },
        deleteAllClass(e){
            e.forEach(item => {
                item.classList.remove('all-checkbox-active')
            })
        },
        setAllItemClass(e){
            console.log(e)
            e.forEach(item =>{
                if(item.value == 'All'){
                    item.classList.remove('all-checkbox-active')
                    item.classList.add('all-item-active')
                }
            })
        },














       getParent(){
        let parent = this.$refs.boxWrapper
        setTimeout(()=>{
            this.getDisabled(parent)
        },1000)
       },
        getDisabled(e){
            // console.log(e)
            if(e.childElementCount == 2){
                for(let k=0; k<e.childElementCount; k++){
                    console.log(e)
                }
            }else{
                let child
                for(let i=0; i<e.length; i++){
                    child = e[i]
                    // console.log(child.childNodes.length)
                }
                    return this.getDisabled(child)
            }
            
        }
    }
}
</script>