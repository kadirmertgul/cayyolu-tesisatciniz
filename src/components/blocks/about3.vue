<script setup>

import { ref } from "vue";

const title = 'Yaşamkent Su Tesisatı'

const body = 'Yaşamkent ve çevresinde Yaşamkent Su tesisatı firması ihtiyacı olan kişiler, firmadan hizmet almadan önce Yaşamkent su tesisatı fiyatları hakkında bilgi almak istemektedir. Yaşamkent su tesisatı firması olarak ön plana çıkmasının yanı sıra Çayyolu genelinde sunmuş olduğu kaliteli hizmet ile de dikkat çeken firmamız, aynı zamanda uygun fiyat güvencesi ile su tesisatı hizmeti vermeyi önemsemektedir. Hizmet verdiği her alanda %100 müşteri memnuniyetini ilk şart olarak kendilerine prensip edinen su tesisatı firmamız, bütçe dostu yaklaşımla Yaşamkent en uygun su tesisatı firması fiyatları ile dikkat çekmektedir.'

const isIntersected = ref(false)

const onIntersect = (a, b) => {
    if(b[0].intersectionRatio >= 0.5)
        isIntersected.value = true
}
</script>

<template>
    <section class="about-main" v-intersect="{handler: onIntersect, options: { threshold: [0, 0.5, 1.0] }}" :class="{intersected: isIntersected}">
        <v-container>
            <div class="d-flex justify-center">
                <h2 class="title">{{ title }}</h2>
            </div>
            <div class="d-flex justify-center">
                <VRow>
                    <VCol cols="12" lg="10" xl="9" class="mx-auto">
                        <div class="body" v-html="body"></div>
                    </VCol>
                </VRow>
            </div>
        </v-container>
    </section>
</template>

<style lang="scss">
    .about-main{
        padding: 50px 0;
        .title{
            font-size: 38px;
            font-weight: 900;
            margin-bottom: 20px;
            line-height: 1.1;
        }
        .body{
            font-size: 16px;
            font-weight: 300;
            margin-bottom: 20px;
            transition: all .8s;
            opacity: .3;
            transform: translateY(80%);
        }
        &.intersected{
            .body{
                opacity: 1;
                transform: translateY(0);
            }
        }
    }
</style>
