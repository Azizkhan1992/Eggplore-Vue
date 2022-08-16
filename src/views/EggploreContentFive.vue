<template>
    <div class="eggplore-five-container">
        <div class="eggplore-five-content">
            <eggplore-slider/>
            <eggplore-tab-bar :headers="tabHeaders" v-slot="slotProps">
                <div class="tab-content-container">
                    <div class="tab-1" v-if="slotProps.active === 'one'">
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. A illo neque eligendi, et ex aspernatur doloribus, praesentium maxime assumenda autem nobis, asperiores ipsa unde distinctio minima nemo. Commodi eos laborum tempore eius impedit ipsum esse odit sit a, ab facere.
                    </div>
                    <div class="tab-2" v-if="slotProps.active === 'two'">
                    <span v-html="message"></span>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. In ipsum praesentium cupiditate culpa. Doloribus natus iste iure doloremque dolorum dicta ipsa ut voluptatem consectetur eos laborum tempora quibusdam, animi modi aspernatur neque omnis alias culpa totam hic inventore nam delectus odit ratione? Minus iusto rerum alias similique soluta laudantium modi?
                    </div>
                    <div class="tab-3" v-if="slotProps.active === 'three'">
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Iure recusandae, necessitatibus placeat ut fugiat a nesciunt sit maiores porro voluptatibus, fuga ipsa, illum aliquid minima cum? Animi reprehenderit ducimus vel?
                    </div>
                    <div class="tab-4" v-if="slotProps.active === 'four'">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Mollitia, iure. Quo cupiditate nesciunt pariatur doloribus alias odio! Reprehenderit, nobis pariatur.
                    </div>
                </div>
            </eggplore-tab-bar>
        </div>
    </div>
</template>
<script>
import EggploreSlider from './eggplore-five/EggploreSlider.vue';
import EggploreTabBar from './eggplore-five/EggploreTabBar.vue';
export default {
    name: 'eggplore-five',
    components:{EggploreSlider, EggploreTabBar},
    data() {
        return {
            message: "<h1>Salom</h1>",
            tabHeaders: [
                {name: "Active", value: 'one', active: true},
                {name: "Inactive", value: 'two', },
                {name: "Inactive", value: 'three'},
                {name: "Inactive", value: 'four'}
            ]
        }
    }
}
</script>