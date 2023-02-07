<template>
<swiper
:slides-per-view="3"
:space-between="10"
>
<swiper-slide>
   <img class="slide" :src="slides" alt="slide">
</swiper-slide>
</swiper>
</template>

<script>
 import { Swiper, SwiperSlide } from "swiper/vue/swiper-vue";
 import { Pagination } from 'swiper';
 import "swiper/swiper.css";
 import 'swiper/swiper-bundle.css';
export default ({
  name: 'Slider',
  components: {
   Swiper,
   SwiperSlide,
   Pagination,
  },
  props: {
    slides: {
      type: String,
      required: true,
    }
  },

})
</script>
<style scoped>
.slide {
  width: 20%;
  height: 20%;
}
</style>
