<script setup>
import service from '../../assets/img/service/service.png'
import circle1 from '../../assets/img/service/circle-1.svg'
import circle2 from '../../assets/img/service/circle-2.svg'
import circle3 from '../../assets/img/service/circle-3.svg'
import dots from '../../assets/dots.svg'
import { ref } from "vue";

const title = 'Yerinde Tespit Hemen Tamir!'
const body = '7/24 araçlarımızla arızanın bulunduğu bölgeye gelip tespitlerimizi yapıp çözümünü sunuyoruz.'
const isIntersected = ref(false)

const onIntersect = (a, b) => {
    if(b[0].intersectionRatio >= 0.5)
        isIntersected.value = true
}
</script>

<template>
  <section class="service-main" v-intersect="{handler: onIntersect, options: { threshold: [0, 0.5, 1.0] }}" :class="{intersected: isIntersected}">
    <VRow>
      <VCol cols="12" md="6" class="ps-md-10 d-flex justify-center align-center position-relative text-col">
        <img :src="circle1" class="circle circle1" />
        <img :src="circle2" class="circle circle2" />
        <img :src="circle3" class="circle circle3" />
        <div class="content-inner">
          <h4>{{ title }}</h4>
          <div class="body" v-html="body"></div>
          <VBtn
            color="warning"
            size="large"
            href="https://wa.me/+905523343071?text=Merhaba%20İsterseniz%20Whatsapp%20Üzerinden%20Arama%20Yapabilirsiniz%20"
            style="text-transform: none; font-size: 13px;"
          >
            Hemen Ara
          </VBtn>
        </div>
      </VCol>
      <VCol md="6" class="d-none d-md-flex position-relative img-col">
        <img :src="service" class="service-img" />
        <img :src="dots" class="dots" />
      </VCol>
    </VRow>
  </section>
</template>

<style lang="scss">
.service-main{
    margin: 50px 0;
    .service-img{
        width: 100%;
    }
    .circle{
        position: absolute;
        &.circle1{
            top: 40%;
            left: 8%;
        }
        &.circle2{
            bottom: 0;
            left: 0;
            transform: translateX(-40%);
        }
        &.circle3{
            bottom: 30%;
            left: 14%;
        }
    }
    .dots{
        position: absolute;
        bottom: 10%;
        left: -6%;
        z-index: -1;
    }
    .content-inner{
        max-width: 350px;
        width: 80%;
        transform: translateY(-40%);
        h4{
            font-size: 38px;
            font-weight: 900;
            margin-bottom: 20px;
            line-height: 1.1;
        }
        .body{
            font-size: 16px;
            font-weight: 300;
            margin-bottom: 20px;
        }
    }

    .img-col{
        opacity: .3;
        transform: translateX(50%);
        transition: opacity .5s, transform .5s;
    }
    .text-col{
        opacity: .3;
        transform: translateX(-50%);
        transition: opacity .5s, transform .5s;
    }
    &.intersected{
        .img-col,
        .text-col{
            opacity: 1;
            transform: translateX(0);
        }
    }
}
</style>
