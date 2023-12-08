<script setup>
import usta from '../../assets/img/campaign/usta.png'
import circle1 from '../../assets/img/campaign/shape-circle-1.svg'
import circle2 from '../../assets/img/campaign/shape-circle-2.svg'
import triangle1 from '../../assets/img/campaign/shape-triangle-1.svg'
import triangle2 from '../../assets/img/campaign/shape-triangle-2.svg'
import triangle3 from '../../assets/img/campaign/shape-triangle-3.svg'
import quota from '../../assets/img/campaign/shape-quota.svg'
import { ref } from "vue";

const body = 'Bakımsız, usta eli değmemiş yapılar sizi bir süre sonra yarı yolda bırakacaktır. <br /> Unutmayın ki tüm bakımları zamanında aksatmadan yapılan eviniz uzun yıllar size sorun çıkarmaz.'

const isIntersected = ref(false)

const onIntersect = (a, b) => {
    if(b[0].intersectionRatio >= 0.5)
        isIntersected.value = true
}

</script>

<template>
  <section class="campaign-main py-12" v-intersect="{handler: onIntersect, options: { threshold: [0, 0.5, 1.0] }}">
    <div class="d-md-block">
      <img :src="circle1" class="visual-img circle-1"/>
      <img :src="circle2" class="visual-img circle-2"/>
      <img :src="triangle1" class="visual-img triangle-1"/>
      <img :src="triangle2" class="visual-img triangle-2"/>
      <img :src="triangle3" class="visual-img triangle-3"/>
      <img :src="quota" class="visual-img quota" />
    </div>
    <v-container class="content-main" :class="{intersected: isIntersected}">
      <VRow>
        <VCol cols="12" md="6" class="img-col">
          <div class="d-flex justify-center justify-md-end align-center pe-4">
            <VImg
              :src="usta"
              max-width="360px"
            />
          </div>
        </VCol>
        <VCol cols="12" md="6" class="text-col">
          <div class="d-flex justify-center justify-md-start align-center w-100 h-100 ps-4">
            <div class="textBody">
              <p v-html="body"></p>
            </div>
          </div>
        </VCol>
      </VRow>
    </v-container>
  </section>
</template>

<style lang="scss">

.campaign-main{
    margin-top: 60px;
    position: relative;
    .content-main{
        position: relative;
        z-index: 2;
        .img-col{
            opacity: .3;
            transform: translateX(-50%);
            transition: opacity .5s, transform .5s;
        }
        .text-col{
            opacity: .3;
            transform: translateX(50%);
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
  .textBody{
      max-width: 260px;
      font-size: 18px;
      font-weight: 300;
      font-style: italic;
  }
    .visual-img{
        position: absolute;
        z-index: 1;
        transform: scale(80%);
        &.circle-1{
            bottom: 0;
            left: 14%;
        }
        &.circle-2{
            top: 0;
            right: 2%;
        }
        &.triangle-1{
            bottom: 20%;
            left: 4%;
        }
        &.triangle-2{
            right: 16%;
            bottom: 40%;
        }
        &.triangle-3{
            bottom: 0;
            right: 10%;
        }
        &.quota{
            top: 14%;
            left: 48%;
        }
    }
    @media screen and (max-width:959px){
        .visual-img{
            &.circle-1{
                left: -10% !important;
            }
        }
    }
}

</style>
