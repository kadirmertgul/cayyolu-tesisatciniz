<script setup>
import image1 from '../../assets/img/kacak-tespiti.png'
import image2 from '../../assets/img/tikaniklik-acma.png'
import image3 from '../../assets/img/kombi-bakimi.png'
import { ref } from "vue";

const serviceList = [
    {
        img: image1,
        title: 'Su Kaçağı Tespiti',
        body: 'Mevsim geçişlerinde kalorüferlerimizin bakımı ile ilgili harekete geçmeliyiz.'
    },
    {
        img: image2,
        title: 'Tıkanıklık Açma',
        body: 'Tıkanan lavobolar, klozetler veya duşlar açılmıyor mu? Çileden çıkmayın, Arayın!'
    },
    {
        img: image3,
        title: 'Kombi Bakım',
        body: 'Kombinizin bakımını bir an önce yaptırın, yüksek faturalardan kurtulun.'
    }
]
const isIntersected = ref(false)

const onIntersect = (a, b) => {
    if(b[0].intersectionRatio >= 0.5)
        isIntersected.value = true
}

</script>

<template>
  <section class="services-main" id="services" v-intersect="{handler: onIntersect, options: { threshold: [0, 0.5, 1.0] }}">
    <v-container>
      <v-row :class="{intersected: isIntersected}">
        <v-col
          cols="12"
          md="4"
          lg="3"
          v-for="(i, k) in serviceList"
          :key="k"
          class="pb-3 pb-md-0 service-col"
        >
          <VCard elevation="12">
            <VCardText>
              <div class="py-6">
                <div class="d-flex justify-center">
                  <VImg
                    :src="i.img"
                    :alt="i.title"
                    max-width="80"
                    aspect-ratio="1"
                  />
                </div>

                <div class="d-flex justify-center pt-4 pb-4">
                  <h4>{{ i.title }}</h4>
                </div>

                <div class="d-flex justify-center px-3 text-center">
                  {{ i.body }}
                </div>
              </div>
            </VCardText>
          </VCard>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<style lang="scss">
  .services-main{
      position: relative;
      z-index: 2;
      .service-col{
          transform: translateY(85%);
          transition: transform .5s;
      }
      .intersected{
          .service-col{
              transform: translateY(0);
          }
      }
  }
</style>
