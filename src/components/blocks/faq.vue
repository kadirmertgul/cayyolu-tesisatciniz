<script setup>
import circle from '../../assets/img/faq/circle.svg'

const faqs = [
    {
        title: 'Elemanlarınız içeri girdiğinde hijyene önem gösteriyor mu?',
        body: 'Tüm elemanlarımız hijyenik koşullarda evinizi ziyaret ederler. Genel hijyen kuralları çerçevesinde önlem alırlar. Ve müşteri çalışan mesafesini korurlar. En ufak bir endişeniz olmasın.'
    },
    {
        title: 'Gece evimi su bassa arayabilir miyim?',
        body: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem exercitationem odit quibusdam voluptatem voluptates. Consequatur, consequuntur corporis error eveniet, expedita placeat quam quia quis quod suscipit tenetur, velit veniam voluptatum.'
    },
    {
        title: 'Başka servisten hizmet aldım, daha çok dert açıldı başıma. Ne yapmalıyım?',
        body: 'Eaque labore molestiae non omnis porro reiciendis tempora voluptas. Ad adipisci amet atque consectetur culpa deleniti fugit iure, labore magnam minima, minus nesciunt numquam porro possimus quaerat quibusdam ratione vero.'
    },
    {
        title: 'Can i cancel what we have deal?',
        body: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem exercitationem odit quibusdam voluptatem voluptates. Consequatur, consequuntur corporis error eveniet, expedita placeat quam quia quis quod suscipit tenetur, velit veniam voluptatum.'
    },
]

</script>

<template>
  <section class="faq-main">
    <img :src="circle" class="circle" />
    <v-container>
      <div class="d-flex justify-center mb-2">
        <h2 class="section-title">Sık Sorulan Sorular</h2>
      </div>
      <VRow>
        <VCol cols="12" md="11" lg="10" xl="9" class="mx-auto py-12">
          <VExpansionPanels>
            <VExpansionPanel
              v-for="(faq, key) in faqs"
              :key="key"
              :title="faq.title"
              :text="faq.body"
              class="my-2"
            />
          </VExpansionPanels>
        </VCol>
      </VRow>
    </v-container>
  </section>
</template>

<style lang="scss">
  .faq-main{
      padding: 0 0 50px 0;
      position: relative;
      .circle{
          position: absolute;
          z-index: -1;
          left: 50%;
          top: 30%;
          width: 100vw;
      }
      .section-title{
          font-size: 36px;
      }
  }
</style>
