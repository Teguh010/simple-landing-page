<template>
  <div class="background-image">
    <div class="home-container">
      <div class="row top-container">
        <div class="col-7 col-md-7 col-xs-12">
          <div class="row">
            <div class="col-md-9">
              <div>
                <transition
                  appear
                  enter-active-class="animated fadeIn slower delay-3s"
                >
                  <div class="q-pb-md">
                    <div style="position: relative">
                      <div class="tooltip-first">풀타임, 파트타임</div>

                      <svg
                        width="12"
                        height="11"
                        viewBox="0 0 12 11"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                        class="icon-tooltip-first"
                      >
                        <path
                          d="M6.43301 10.25C6.24056 10.5833 5.75944 10.5833 5.56699 10.25L0.370835 1.25C0.178386 0.916665 0.418948 0.499999 0.803848 0.499999L11.1962 0.5C11.5811 0.5 11.8216 0.916667 11.6292 1.25L6.43301 10.25Z"
                          fill="currentColor"
                        ></path>
                      </svg>
                    </div>
                  </div>
                </transition>

                <transition
                  appear
                  enter-active-class="animated fadeInUp slower"
                >
                  <div class="main-title q-pb-md">
                    최고의 실력을 가진 <br />
                    외국인 인재를 찾고 계신가요?
                  </div>
                </transition>
              </div>
              <div>
                <transition
                  appear
                  enter-active-class="animated fadeInUp slower"
                >
                  <div class="second-title q-py-md">
                    법률 및 인사관리 부담없이 1주일 이내에 원격으로
                    채용해보세요.
                  </div>
                </transition>
              </div>
              <div>
                <transition
                  appear
                  enter-active-class="animated fadeInUp slower"
                >
                  <div class="only-desktop third-title q-py-md">
                    개발자가 필요하신가요?
                  </div>
                </transition>
              </div>

              <div class="only-desktop">
                <transition appear enter-active-class="fadeinatonce ">
                  <div
                    class="flex hero-cards-container q-py-md fadein-atonce-500"
                  >
                    <q-card class="hero-card" flat>
                      <q-separator  color="white" />
                      <q-card-section class="hero-section-card">
                        <div class="third-title">평균 월 120만원</div>
                        <div class="forth-title">
                          임금을 해당 국가를 기준으로 계산합니다.
                        </div>
                      </q-card-section>
                    </q-card>
                    <q-card class="hero-card q-pl-md" flat>
                      <q-separator inset color="white" />
                      <q-card-section >
                        <div class="third-title">최대 3회 인력교체</div>
                        <div class="forth-title">
                          막상 채용해보니 맞지 않아도 걱정하지 마세요.
                        </div>
                      </q-card-section>
                    </q-card>
                    <q-card class="hero-card" flat>
                      <q-separator inset color="white" />
                      <q-card-section >
                        <div class="third-title">평균 3일, 최대 10일</div>
                        <div class="forth-title">
                          급하게 사람이 필요한 경우에도 빠른 채용이 가능합니다.
                        </div>
                      </q-card-section>
                    </q-card>
                  </div>
                </transition>
              </div>
            </div>
          </div>
        </div>
        <div class="col-xs-12 col-sm-12 col-md-5 col-lg-5 col-xl-5">
          <CoverflowSlider />
        </div>
      </div>
      <div class="only-desktop">
        <transition appear enter-active-class="fadeinx">
          <div class="slider-hero-small fadein-500">
            <GeneralSlider />
          </div>
        </transition>
      </div>
      <div
        class="column q-pl-md only-mobile"
        style="gap: 8px; margin-bottom: 20px; font-size: 16px"
      >
        <div class="flex" style="gap: 8px">
          <div class="flex checkbox-text" style="gap: 12px">
            <q-icon style="font-size: 20px">
              <img src="~assets/checkbox.svg" />
            </q-icon>

            한국어 능력
          </div>
          <div class="flex checkbox-text" style="gap: 12px">
            <q-icon style="font-size: 20px">
              <img src="~assets/checkbox.svg" />
            </q-icon>

            업무 수행 능력
          </div>
        </div>
        <div class="flex checkbox-text" style="gap: 8px">
          <div class="flex" style="gap: 12px">
            <q-icon style="font-size: 20px">
              <img src="~assets/checkbox.svg" />
            </q-icon>

            겸업 여부
          </div>
          <div class="flex checkbox-text" style="gap: 12px">
            <q-icon style="font-size: 20px">
              <img src="~assets/checkbox.svg" />
            </q-icon>

            평판 조회
          </div>
        </div>
        <div class="highlighted-text">개발자가 필요하신가요?</div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';
import CoverflowSlider from 'src/components/CoverflowSwiper.vue';
import GeneralSlider from 'src/components/GeneralSwiper.vue';

export default {
  components: {
    CoverflowSlider,
    GeneralSlider,
  },
  setup() {
    const showTooltip = ref(false);
    const showMainTitle = ref(true);
    const slide = ref(1);

    // Menggunakan onMounted untuk lifecycle hook
    onMounted(() => {
      setTimeout(() => {
        showTooltip.value = true;
      }, 300);
    });

    return {
      showTooltip,
      showMainTitle,
      slide,
    };
  },
};
</script>

<style>
.home-container {
  padding: 100px 20px 0px 20px;
}
.background-image {
  width: 100%;
}

/* Style untuk teks */
.background-image h1 {
  color: white;
  font-size: 2rem;
}
.main-title {
  font-weight: 900;
  font-size: 48px;
  line-height: 62.4px;
  color: white;
}
.second-title {
  font-weight: 900;
  font-size: 24px;
  line-height: 34px;
  color: rgba(255, 255, 255, 0.9);
}
.third-title {
  font-weight: 900;
  font-size: 18px;
  line-height: 27px;
  color: rgba(255, 255, 255, 1);
}
.hero-card {
  background: transparent !important;
  width: 180px !important;
}
.hero-section-card {
  padding: 16px 0px !important;
}
.forth-title {
  font-weight: 900;
  font-size: 16px;
  line-height: 24px;
  color: rgba(255, 255, 255, 0.8);
}
.top-container {
  max-width: 1280px;
  margin: 0 auto;
}

/* animation */

.fadeinup {
  animation: fadeinup-animation 500ms ease-out;
}

@keyframes fadeinup-animation {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fadeinatonce {
  animation: fadein-atonce 500ms ease-out forwards;
}

@keyframes fadein-atonce {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0); /* Kembali ke posisi asli */
  }
}

.fadeinx {
  animation: fadeinx 500ms ease-out forwards;
}

@keyframes fadeinx {
  from {
    opacity: 0;
    transform: translateX(-40px);
  }
  to {
    opacity: 1;
    transform: translateY(0); /* Kembali ke posisi asli */
  }
}

.fadeinup-1000 {
  animation: fadeinup-1000-animation 500ms ease-out;
}

@keyframes fadeinup-1000-animation {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.tooltip-first {
  font-size: 18px;
  font-weight: 600;
  width: fit-content;
  padding: 6px 12px;
  border-radius: 8px;
  color: rgba(139, 196, 255, 1);
  background-color: white;
}

.icon-tooltip-first {
  position: absolute;
  bottom: -9px;
  left: 9px;
  color: white;
}

@media (max-width: 768px) {
  .top-container {
    padding: 0 10px;
    max-width: 100%;
  }
  .only-desktop {
    display: none;
  }
  .tooltip-first {
    background: rgba(139, 196, 255, 1);
    color: white;
  }
  .icon-tooltip-first {
    position: absolute;
    bottom: -9px;
    left: 9px;
    color: rgba(139, 196, 255, 1);
  }
  .home-container {
    padding: 20px 10px 0px 10px;
  }
  .main-title {
    font-weight: 900;
    font-size: 36px;
    line-height: 46px;
    color: white;
  }
  .second-title {
    font-weight: 900;
    font-size: 18px;
    line-height: 34px;
    color: rgba(255, 255, 255, 0.9);
  }
}

@media (min-width: 1100px) {
  .only-mobile {
    display: none;
  }
}
.checkbox-text {
  color: rgba(255, 255, 255, 1);
  font-size: 16px;
  font-weight: 900;
}
.highlighted-text {
  font-weight: 900;
  font-size: 16px;
  margin-top: 16px;
  color: rgba(251, 255, 35, 1);
}
</style>
