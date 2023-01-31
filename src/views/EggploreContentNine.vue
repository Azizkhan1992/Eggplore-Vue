<template>
    <div class="carousel-slider-container">
      <div class="carousel-slider-content">
        <div class="owl-carousel-wrapper">
          <div class="carousel-item" v-for="slide in carousel" :key="slide.id"
          :class="slide.id === carousel[2].id ? 'center' : '' ||
          slide.id === carousel[0].id ? 'hiddenL' : '' ||
          slide.id === carousel[4].id ? 'hiddenR' : ''
          "
          >
          <!-- :style="item_style" -->
            <img :src="require('@/assets/Content-nine/' + slide.img)" alt="">
            <h3>{{slide.name}}</h3>
            <p>{{slide.title}}</p>
            <button>{{slide.button}}</button>
          </div>
        </div>
      </div>
    </div>
</template>
<script>


export default {
    name: 'carousel-slider',
    data(){
        return{
            hidden: false,
            counter: 1,
            item_width: 150,
            margin_right: 15,
            container_max_width: 825,
            carousel:[
        {
          id: 1,
          name: "Футбол",
          img: 'img1.png',
          background_img: 'Vector1.png',
          title:
            "Футбо́л (англ. football от foot «ступня» + ball «мяч») — командный вид спорта, в котором целью является забить ...",
          button: "Подробнее",
        },
        {
          id: 2,
          name: "Теннис",
          img: 'img2.png',
          background_img: 'Vector2.png',
          title:
            "Те́ннис (англ. tennis) или большо́й теннис — вид спорта, в котором соперничают либо два игрока ...",
          button: "Подробнее",
        },
        {
          id: 3,
          name: "Баскетбол",
          img: 'img3.png',
          background_img: 'Vector3.png',
          title:
            "Баскетбо́л — спортивная командная игра с мячом, в которой мяч забрасывают руками в кольцо соперника.",
          button: "Подробнее",
        },
        {
          id: 4,
          name: "Хоккей",
          img: 'img4.png',
          background_img: 'Vector4.png',
          title:
            "Хокке́й (англ. hockey) — семейство игр на ледовой, тартановой, пластиковой, деревянной или травяной площадке, в котором две команды ...",
          button: "Подробнее",
        },
        {
          id: 5,
          name: "Бокс",
          img: 'img5.png',
          background_img: 'Vector5.png',
          title:
            "Бокс (от фр. boxe — «бокс» и boxeur — «боксёр», которые происходят от англ. to box — «драться на ринге», «боксировать»...",
          button: "Подробнее",
        },
      ],
        }
    },
    mounted(){
      this.play()
      // this.carousel_push()
    },
    computed:{
      item_style(){
        return {
          width: `${this.item_width + 'px'}`,
          marginRight: `${this.margin_right + 'px'}`
        }
      },
      container_style(){
        return{
          maxWidth: `${this.container_max_width + 'px'}`
        }
      },
      wrapper_style(){
        return{
          width: (this.carousel.length * (this.item_width + this.margin_right)) + 'px'
        }
      },
      // transformStep(){
      //   const step_size = this.move_left * (this.item_width + this.margin_right)
      //   return{transform: `translate3d(${-1* step_size}px, 0, 0)`}
      // },
      // left_side(){
      //   return JSON.parse(JSON.stringify(this.owl_carousel.slice(0, 3)))
      // },
      // move_left(){
      //   return this.left_side.length + this.counter
      // },
      // right_side(){
      //   return JSON.parse(JSON.stringify(this.owl_carousel.slice(-3,-1)))
      // },
      // carousel(){
      //   return [...this.left_side, ...this.owl_carousel, ...this.right_side]
      // }
    },
    methods:{
      play(){
        setInterval(() => {
          this.animation()
          this.hidden = false
        }, 4000)
      },
      animation(){
        let item = this.carousel.shift(),
        len = this.carousel.length

        
        this.carousel.push(item)
        // this.hidden = false
        
        if(this.counter <= len){
          this.counter++
        } else this.counter = 1
      }
    }
}
</script>
<style>
/* .animate-item{
  position: relative;
  display: flex;
  flex-direction: row;
  gap: 20px;
  height: 440px;
  width: 100vw !important;
} */
</style>