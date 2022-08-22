<template>
    <div class="carousel-slider-container">
        <eggplore-carousel-slider :slides="owl_carousel"></eggplore-carousel-slider>
    </div>
</template>
<script>
import EggploreCarouselSlider from './eggplore-nine/EggploreCarouselSlider.vue';
export default {
    name: 'carousel-slider',
    components: {EggploreCarouselSlider},
    data(){
        return{
            visibleSlide: 0,
            owl_carousel:[
        {
          id: 1,
          name: "Футбол",
          img: 'img1.jpg',
          background_img: 'Vector1.png',
          title:
            "Футбо́л (англ. football от foot «ступня» + ball «мяч») — командный вид спорта, в котором целью является забить ...",
          button: "Подробнее",
        },
        {
          id: 2,
          name: "Футбол",
          img: 'img1.png',
          background_img: 'Vector1.png',
          title:
            "Футбо́л (англ. football от foot «ступня» + ball «мяч») — командный вид спорта, в котором целью является забить ...",
          button: "Подробнее",
        },
        {
          id: 3,
          name: "Теннис",
          img: 'img2.png',
          background_img: 'Vector2.png',
          title:
            "Те́ннис (англ. tennis) или большо́й теннис — вид спорта, в котором соперничают либо два игрока ...",
          button: "Подробнее",
        },
        {
          id: 4,
          name: "Баскетбол",
          img: 'img3.png',
          background_img: 'Vector3.png',
          title:
            "Баскетбо́л — спортивная командная игра с мячом, в которой мяч забрасывают руками в кольцо соперника.",
          button: "Подробнее",
        },
        {
          id: 5,
          name: "Хоккей",
          img: 'img4.png',
          background_img: 'Vector4.png',
          title:
            "Хокке́й (англ. hockey) — семейство игр на ледовой, тартановой, пластиковой, деревянной или травяной площадке, в котором две команды ...",
          button: "Подробнее",
        },
        {
          id: 6,
          name: "Бокс",
          img: 'img5.png',
          background_img: 'Vector5.png',
          title:
            "Бокс (от фр. boxe — «бокс» и boxeur — «боксёр», которые происходят от англ. to box — «драться на ринге», «боксировать»...",
          button: "Подробнее",
        },
        {
          id: 7,
          name: "Бокс",
          img: 'img5.jpg',
          background_img: 'Vector5.png',
          title:
            "Бокс (от фр. boxe — «бокс» и boxeur — «боксёр», которые происходят от англ. to box — «драться на ринге», «боксировать»...",
          button: "Подробнее",
        },
      ],
        }
    }
}
</script>