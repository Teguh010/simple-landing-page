<template>
  <q-layout view="hhh lpR fff" class="layout-background">
    <div class="header-container">
      <q-header class="bg-transparent main-header">
        <q-toolbar>
          <q-toolbar-title>
            <div>
              <img style="width: 120px" src="~assets/HipeHireLogo.png" />
            </div>
          </q-toolbar-title>
          <q-space class="spacer" />
          <div class="only-desktop">
            <q-btn color="white" flat icon-right="expand_more">
              <span class="header-label"> {{ selectedMenu.label }}</span>
              <q-menu>
                <q-list style="min-width: 100px">
                  <q-item
                    v-for="(item, index) in menuItems"
                    :key="index"
                    clickable
                    v-close-popup
                    @click="updateSelectedMenu(item)"
                  >
                    <q-item-section
                      :class="
                        selectedMenu.label === item.label ? 'text-bold' : ''
                      "
                      >{{ item.label }}</q-item-section
                    >
                  </q-item>
                  <q-separator />
                  <q-item clickable v-close-popup>
                    <q-item-section>한국어 가능 외국인 채용</q-item-section>
                  </q-item>
                </q-list>
              </q-menu>
            </q-btn>
          </div>
          <div class="only-mobile">
            <q-btn flat @click="drawerRight2 = true" round dense icon="menu" />
          </div>
          <div class="q-pl-xl only-desktop">
            <span class="header-label"> 해외 개발자 활용 서비스 </span>
          </div>
          <q-space class="only-desktop" />
          <div class="only-desktop">
            <q-btn
              style="border-radius: 8px"
              class="bg-white text-primary no-box-shadow text-bold"
              label="문의하기"
              flat
            />
          </div>
        </q-toolbar>
      </q-header>
    </div>
    <q-footer style="background: #fbfbfb">
      <div class="main-footer">
        <FooterContent />
      </div>
    </q-footer>

    <q-drawer side="right" v-model="drawerRight2" bordered overlay :width="200">
      <q-scroll-area class="fit">
        <div class="q-pa-sm">
          <q-list style="min-width: 100px">
            <q-item
              v-for="(item, index) in menuItems2"
              :key="index"
              clickable
              v-close-popup
              @click="updateSelectedMenu(item)"
            >
              <q-item-section
                :class="selectedMenu.label === item.label ? 'text-bold' : ''"
                >{{ item.label }}</q-item-section
              >
            </q-item>
            <q-separator />
            <q-item clickable v-close-popup>
              <q-item-section class="text-bold"
                >해외 개발자 활용 서비스</q-item-section
              >
            </q-item>
            <div class="q-pt-lg">
              <q-btn
                dense
                flat
                class="bg-secondary text-white full-width"
                style="border-radius: 8px"
              >
                문의하기
              </q-btn>
            </div>
          </q-list>
        </div>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import FooterContent from 'src/components/FooterContent.vue';
import { ref } from 'vue';

const drawerRight2 = ref(false);

const menuItems = ref([
  { label: '채용', color: 'primary' },
  { label: '해외 개발자 원격 채용', color: 'secondary' },
  { label: '외국인 원격 채용 (비개발 직군)', color: 'primary' },
]);

const menuItems2 = ref([
  { label: '채용', color: 'primary' },
  { label: '해외 개발자 원격 채용', color: 'secondary' },
  { label: '외국인 원격 채용 (비개발 직군)', color: 'primary' },
  { label: ' 한국어 가능 외국인 채용', color: 'primary' },
]);

const selectedMenu = ref(menuItems.value[0]); // Default adalah item pertama

function updateSelectedMenu(item) {
  selectedMenu.value = item;
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

.header-label {
  font-weight: 900;
  font-size: 16px;
  line-height: 24px;
  color: #ffffff;
}

.layout-background {
  font-family: 'Poppins', sans-serif !important;
  background: linear-gradient(151.17deg, #26c2b9 8.69%, #288be7 126.06%);
}
.main-header {
  max-width: 1400px;
  margin: 0 auto;
  padding: 15px 0px;
}

.main-footer {
  max-width: 1400px;
  margin: 0 auto;
}

@media (max-width: 768px) {
  .layout-background {
    font-family: 'Poppins', sans-serif !important;
    background: linear-gradient(
      151.17deg,
      #26c2b9 8.69%,
      #288be7 126.06%
    ) !important;
  }
  .spacer {
    display: none;
  }
  .only-desktop {
    display: none;
  }
  .main-header {
    max-width: 100%;
    padding: 10px;
  }
}
</style>
