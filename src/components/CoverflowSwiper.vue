<template>
  <div>
    <div>
      <transition appear enter-active-class="animated slower fadeIn delay-3s">
        <div class="tooltip-sidebar-container">
          <div class="bg-white flex items-center tooltip-slider">
            <q-icon class="icon-dollar" style="font-size: 25px">
              <img src="~assets/Dollar.svg" />
            </q-icon>

            월 100만원
          </div>
          <q-icon class="icon-tooltip-second">
            <img src="~assets/Polygon.svg" />
          </q-icon>
        </div>
      </transition>
    </div>
    <div>
      <swiper
        :slides-per-group="1"
        :initial-slide="1"
        class="swiper"
        :modules="modules"
        :effect="'coverflow'"
        :grab-cursor="true"
        :centered-slides="true"
        :navigation="true"
        :space-between="0"
        :slides-per-view="$q.screen.lt.md ? 1.4 : 2.3"
        :coverflow-effect="{
          rotate: 0,
          stretch: $q.screen.lt.md ? 200 : 160,
          depth: 150,
          modifier: 1,
          slideShadows: true,
        }"
        :loop="false"
      >
        <!-- stretch: 220, -->

        <swiper-slide v-for="index in 3" :key="index">
          <!-- <div class="arrow">풀타임, 파트타임</div> -->
          <div class="slide">
            <div class="image-avatar-container">
              <q-avatar size="120px">
                <img style="width: 120px" src="~assets/example-photo.png" />
              </q-avatar>
              <img
                style="width: 20px"
                class="image-badge"
                src="~assets/country-flag.png"
              />
            </div>
            <div class="name">
             Abhishek Gupta
            </div>
            <div class="experience">마케팅 · 2y+</div>

            <div class="description">
              <div class="text">마케팅 콘텐츠 제작</div>
              <div class="text">인스타그램 관리</div>
              <div class="row" style="gap: 5px">
                <div class="text">트위터 관리</div>
                <div class="text q-mr-sm">블로그 글 작성</div>
              </div>
            </div>
          </div>
        </swiper-slide>
      </swiper>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { EffectCoverflow, Navigation } from 'swiper/modules';

import 'swiper/css';
import 'swiper/css/effect-coverflow';
import 'swiper/css/navigation';

export default defineComponent({
  name: 'ProfileSwiper',
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [EffectCoverflow, Navigation],
    };
  },
});
</script>

<style lang="scss" scoped>
.image-avatar-container {
  position: relative;
}
.image-badge {
  position: absolute;
  right: 2px;
  bottom: 15px;
}
.swiper {
  height: 100%;
  width: 100%;
  padding-top: 20px;
  padding-bottom: 50px;

  .slide {
    // max-width: 280px;
    // width: 250px;

    background-color: white;
    color: black;
    border-radius: 10px;
    border: 1px solid transparent !important;
    padding: 30px 0px;

    display: flex;
    justify-content: flex-start;
    align-items: center;
    flex-direction: column;

    @media (max-width: 1200px) {
      // width: 230px;
    }
  }

  .name {
    font-weight: 800;
    font-size: 22px;
    margin-top: 20px;
  }

  .experience {
    font-weight: 600;
    color: #4a77ff;
  }

  .text {
    border: 1px solid #c1c5cf;
    border-radius: 5px;
    padding: 4px 8px;
    display: inline-block;
  }

  .description {
    display: flex;
    flex-direction: column;
    gap: 5px;
    align-items: center;
    padding-top: 20px;
  }

  & .arrow {
    position: absolute;
    top: -50px;
    left: 32%;

    &::after {
      left: 45%;
    }
  }
}

.swiper-slide-shadow-coverflow {
  background-image: linear-gradient(
    to right,
    rgba(0, 0, 0, 0.2),
    rgba(0, 0, 0, 0) !important
  );
}
.icon-tooltip-second {
  position: absolute;
  bottom: -9px;
  left: 50%;
  color: rgba(255, 255, 255, 1);
}
</style>

<style>
@media (max-width: 768px) {
  .swiper-button-next,
  .swiper-rtl .swiper-button-prev {
    right: var(--swiper-navigation-sides-offset, -8px) !important;
    left: auto;
  }
  .swiper-button-prev,
  .swiper-rtl .swiper-button-next {
    left: var(--swiper-navigation-sides-offset, -8px) !important;
    left: auto;
  }
}

@media (min-width: 769px) {
  .swiper-button-next,
  .swiper-rtl .swiper-button-prev {
    right: var(--swiper-navigation-sides-offset, 20px) !important;
    left: auto;
  }
  .swiper-button-prev,
  .swiper-rtl .swiper-button-next {
    left: var(--swiper-navigation-sides-offset, 20px) !important;
    left: auto;
  }
}
.swiper-button-prev:after,
.swiper-button-next:after {
  font-size: 20px;
  font-weight: bold;
  color: white !important;
}
.tooltip-slider {
  font-size: 18px;
  width: fit-content;
  padding: 6px 12px;
  border-radius: 8px;
  gap: 8px;
  font-weight: 900;
  color: rgba(0, 198, 150, 1);
}
.tooltip-sidebar-container {
  position: relative;
  width: fit-content;
  margin: 0px auto;
  padding-top: 20px;
}
</style>
