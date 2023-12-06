<script setup>
import bgYellow from "./../../assets/header_yellow.svg"
import headerMask from "./../../assets/header_mask.png"

import { computed, onMounted, ref } from "vue";

const isSmall = ref(window.innerWidth < 960)
const title = 'Tesisatçınız Bir Telefon Kadar Yakın...'
const body = 'Çayyolu - Ümitköy - Yaşamkent civarındaki tüm işlemlere anında müdahale. <br /> Hemen tıkla. <br /> İster mail ile ister telefonla anında kapında...'
const buttons = [
    {
        title: 'Hemen Ara',
        url: 'tel:+905523343071',
        variant: 'elevated',
        color: 'secondary'
    },
    {
        title: 'Whatsapp',
        url: 'https://wa.me/+905523343071?text=Merhaba%20İsterseniz%20Whatsapp%20Üzerinden%20Arama%20Yapabilirsiniz%20', 
        variant: 'outlined',
        color: 'secondary'
    }
]
const phone = '0 552 334 30 71'

const callTo = computed(() => {
    return 'tel:+9' + (phone.split(' ').join(''))
})


const handleResize = () => {
    isSmall.value = window.innerWidth < 960
}
onMounted(() => {
    window.addEventListener('resize', handleResize)
})

</script>

<template>
  <section class="welcome-main" id="home">
    <img :src="bgYellow" class="bg_yellow d-none d-md-block" />
    <img :src="headerMask" class="header_mask d-none d-md-block" />
    <v-container>
      <div class="welcome-container">
        <h1>{{ title }}</h1>
        <div class="body" v-html="body" />
        <div class="d-flex py-2 justify-center justify-sm-start flex-column flex-sm-row">
          <div v-for="(i, k) in buttons" :key="k" class="py-1 py-md-0 px-md-2">
            <v-btn
              :href="i.url"
              :variant="i.variant"
              :color="i.color"
              :size="isSmall ? 'default' : 'large'"
            >{{ i.title }}</v-btn>
          </div>
        </div>
        <a :href="callTo" class="callTo">{{ phone }}</a>
      </div>
    </v-container>
  </section>
</template>

<style lang="scss">
.bg_yellow {
    min-height: 140%;
    position: absolute;
    bottom: -40%;
    left: 0;
    z-index: 1;
}
.header_mask{
    position: absolute;
    top: 0;
    right: 0;
    max-width: 50vw;
    max-height: 100%;
    z-index: 2;
}
.welcome-main{
    position: relative;
    z-index: 1;
    padding-top: 200px;
    @media screen and (max-width:959px){
        padding-top: 120px;
        &:before{
            content: " ";
            display: block;
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 120%;
            background: #ffd602;
        }
    }
}
  .welcome-container{
      position: relative;
      z-index: 10;
    padding: 0 40% 0 8%;
      h1{
          font-size: 55px;
          font-weight: 900;
          line-height: 1.2;
          color: #000;
          margin: 0 0 10px 0;
      }
      .body{
          font-size: 18px;
          color: #000;
          font-weight: 500;
          line-height: 1.6;
          margin-bottom: 10px;
      }
      .callTo {
          font-size: 40px;
          color: #000;
          font-weight: bold;
          text-decoration: none;
      }
      @media screen and (max-width:959px){
          padding: 0 2%;
          h1{
              font-size: 35px;
              margin: 0 0 10px 0;
          }
          .body{
            font-size: 16px;
          }
      }
  }
</style>
