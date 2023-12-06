<script setup>
import circle from '../../assets/img/faq/circle.svg'

const faqs = [
    {
        title: 'Elemanlarınız içeri girdiğinde hijyene önem gösteriyor mu?',
        body: 'Tüm elemanlarımız hijyenik koşullarda evinizi ziyaret ederler. Genel hijyen kuralları çerçevesinde önlem alırlar. Ve müşteri çalışan mesafesini korurlar. En ufak bir endişeniz olmasın.'
    },
    {
        title: 'Gece evimi su bassa arayabilir miyim?',
        body: '7/24 ekiplerimiz hizmetinizde. Telefonla sizleri yönlendirip. Arızanın devam etmemesini sağladıktan sonra mesai saatleri içerisinde öncelikli olarak sizlere ulaşacaktır.'
    },
    {
        title: 'Başka servisten hizmet aldım, daha çok dert açıldı başıma. Ne yapmalıyım?',
        body: 'Her servis yetkili servis değildir. Gelen arkadaşlara yetkilerini ve belgelerini mutlaka sorunuz. Alanında deneyimli personelimiz ile bu sorunları yaşamayacağınızı bilerek, gönül rahatlığı ile bizleri arayabilirsiniz.'
    },
    {
        title: 'Evimin duvarlarında su sızıntısı var, ne yapmalıyım?',
        body: 'Duvarlarınızı kırmadan son teknoloji su kaçağı tespit makinaları ile önce su kaçağının kaynağını tespit ediyoruz. Sonra tamirini yapıp, bozulan duvarlarınızın kendi renginde boyadıktan sonra tertemiz teslim ediyoruz.'
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
