<script setup>
import logo from "./../../assets/logo.png"
import { onMounted, ref, watch, watchEffect } from "vue";

const windowWidth = ref(window.innerWidth)
const draverVisible = ref(false)
const atTop = ref(true)
const scrollTransformOffset = 40
const menu = [
    {
        title: 'Anasayfa',
        url: '#main'
    },
    {
        title: 'Hizmetler',
        url: '#services'
    },
    {
        title: 'İletişim',
        url: '#contact'
    }
]

const handleResize = () => {
    windowWidth.value = window.innerWidth
}
const handleScroll = () => {
    atTop.value = window.scrollY <= scrollTransformOffset
}

onMounted(() => {
    window.addEventListener('resize', handleResize)
    window.addEventListener('scroll', handleScroll)
})


watchEffect(() => {
    draverVisible.value = windowWidth.value >= 960 ? false : draverVisible.value
})

</script>

<template>
  <section>
    <header :class="{scrolled: !atTop}">
      <v-container>
        <div class="d-flex py-1 py-md-8 justify-space-between justify-md-start header-main">
          <div class="logo-main">
            <a href="/">
              <img :src="logo" class="logo" alt="Çayyolu Tesisatçısı Logo" />
            </a>
          </div>
          <div class="d-flex d-md-none align-center">
            <v-btn
              variant="outlined"
              color="secondary"
              size="40"
              @click="draverVisible = !draverVisible"
            >
              <v-icon icon="mdi-menu"></v-icon>
            </v-btn>
          </div>
          <div class="menu d-none d-md-block flex-shrink-0 flex-grow-0 ps-5 pt-4">
            <v-row>
              <v-col v-for="(i , k) in menu" :key="k">
                <v-btn variant="text" class="menu-item" :href="i.url">{{ i.title }}</v-btn>
              </v-col>
            </v-row>
          </div>
        </div>
      </v-container>
    </header>
    <v-navigation-drawer v-model="draverVisible" class="drawer-main">
      <v-btn
        variant="outlined"
        @click="draverVisible = !draverVisible"
        size="40"
        icon="mdi-close"
        class="drawer-closer"
      >
      </v-btn>
      <div class="py-3">
        <div class="drawer-logo d-flex justify-center">
          <a href="/">
            <img :src="logo" class="logo" alt="Çayyolu Tesisatçısı Logo" />
          </a>
        </div>
        <div class="py-3">
          <v-list-item
            v-for="(i, k) in menu"
            :key="k"
            link
            :href="i.url"
            :title="i.title" />
        </div>
      </div>
    </v-navigation-drawer>
  </section>
</template>

<style lang="scss">
.drawer-main{

    .drawer-closer{
        position: absolute;
        top: 5px;
        right: 5px;
    }
    .logo{
        width: 100px !important;
    }
}
  header{
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 100;
      transition: all .3s;
      .logo {
          width: 180px;
          transition: all .3s;
      }
      .menu-item{
          color: #323232;
          text-transform: none !important;
          font-size: 15px;
      }
      &.scrolled{
          background: rgba(249, 250, 253, .6);
          -webkit-backdrop-filter: blur(4px);
          backdrop-filter: blur(4px);
          .header-main{
              padding-top: 0 !important;
              padding-bottom: 0 !important;
          }
          .logo-main{
              .logo{
                  width: 110px;
              }
          }
      }
      @media screen and (max-width:959px){
          background: rgba(249, 250, 253, .4) !important;
          -webkit-backdrop-filter: blur(4px);
          backdrop-filter: blur(4px);
          .header-main{
              padding-top: 0 !important;
              padding-bottom: 0 !important;
          }
          .logo{
              width: 100px !important;
          }
      }
  }
</style>
