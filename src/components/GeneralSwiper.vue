<template>
  <div class="swiper-container">
    <swiper
      :modules="modules"
      :loop="true"
      :spaceBetween="30"
      :grabCursor="true"
      :centeredSlides="false"
      :autoplay="{
        delay: 5000,
        disableOnInteraction: false,
      }"
      :slidesPerView="4.5"
      class="general-swiper"
    >
      <swiper-slide v-for="(item, index) in items" :key="index">
        <q-list>
          <q-item clickable v-ripple class="item-slider">
            <q-item-section avatar>
              <img style="width: 55px" :src="item.icon" />
            </q-item-section>
            <q-item-section class="list-content-text"
              >{{ item.text }}</q-item-section
            >
          </q-item>
        </q-list>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';

import 'swiper/css/effect-coverflow';
import 'swiper/css/navigation';

// import required modules
import { Autoplay } from 'swiper/modules';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      items: [
        { icon: 'https://i.postimg.cc/vZW0zSFB/Monitor-Icon.png', text: '해외 마케팅' },
        { icon: 'https://i.postimg.cc/xCdg9fkJ/Cube.png', text: '캐드원(제도사)' },
        { icon: 'https://i.postimg.cc/hGspFzGR/Compas.png', text: '해외 세일즈' },
        { icon: 'https://i.postimg.cc/7hFN1SK0/Phone.png', text: '해외 CS' },
        { icon: 'https://i.postimg.cc/RFbdFkfP/Photo.png', text: '퍼블리셔' },
      ],
      modules: [Autoplay],
    };
  },
};
</script>
<style scoped>
.swiper-container {
  width: 100%;
  max-height: 200px;
}

.swiper-slide {
  background-position: center;
  background-size: cover;
  width: 300px;
  height: 300px;
}

.swiper-slide img {
  display: block;
  width: 100%;
}
.item-slider {
  background: rgba(255, 255, 255, 0.2);
  border-radius: 8px;
  padding: 15px;
}
.list-content-text {
  font-weight: 900;
  font-size: 24px;
  line-height: 24px;
  color: #ffffff;
}
</style>
