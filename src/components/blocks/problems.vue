<script setup>
import bg from '../../assets/img/problems/rectangle-bg.svg'
import circle1 from '../../assets/img/problems/circle-1.svg'
import circle2 from '../../assets/img/problems/circle-2.svg'
import circle3 from '../../assets/img/problems/circle-3.svg'
import circle4 from '../../assets/img/problems/circle-4.svg'

const title = 'Nelere Dikkat Etmeliyiz?'
const body = 'Merak ettiğiniz tüm sorularınızı yanıtlamak için size bir telefon kadar yakınız. Hemen arayın!'

</script>

<template>
  <section class="problems-main">
    <img :src="bg" alt="Nelere dikkat etmeliyiz" class="bg"/>
    <v-container class="container-main">
      <VRow>
        <VCol cols="12" md="5" class="d-flex align-center content-main order-md-2">
          <div class="content-inner">
            <h2>{{ title }}</h2>
            <div class="body" v-html="body"></div>
            <VBtn
              color="error"
              size="large"
              href="https://wa.me/+905523343071?text=Merhaba%20İsterseniz%20Whatsapp%20Üzerinden%20Arama%20Yapabilirsiniz%20"
              style="text-transform: none; font-size: 13px;"
            >
              Sorun Nedir?
            </VBtn>
          </div>
        </VCol>
        <VCol cols="10" md="7" lg="6" xl="5" class="img-container order-md-1 mx-auto mx-md-0">
          <img :src="circle1" class="circle circle1"/>
          <img :src="circle2" class="circle circle2"/>
          <img :src="circle3" class="circle circle3"/>
          <img :src="circle4" class="circle circle4"/>
          <VRow>
            <VCol cols="6">
              <VCard
                color="warning"
                class="mb-6 text-card"
              >
                <VCardText class="d-flex justify-center"><span class="card-inner">Banyo Duşundan Az Su Geliyor.</span></VCardText>
              </VCard>
              <VCard
                color="warning"
                class="text-card"
              >
                <VCardText class="d-flex justify-center"><span class="card-inner">Yukarıdaki Banyodan Bizim Tavana Su Akıyor.</span></VCardText>
              </VCard>
            </VCol>
            <VCol cols="6" class="pt-12">
              <VCard
                color="warning"
                class="mb-6 text-card"
              >
                <VCardText class="d-flex justify-center"><span class="card-inner">Lavabo Bir Türlü Açılmıyor.</span></VCardText>
              </VCard>
              <VCard
                color="warning"
                class="text-card"
              >
                <VCardText class="d-flex justify-center"><span class="card-inner">Kombiyi Son Ayarda Yakıyorum Ev Isınmıyor.</span></VCardText>
              </VCard>
            </VCol>
          </VRow>
        </VCol>
      </VRow>
    </v-container>
  </section>
</template>

<style lang="scss">
.problems-main {
    position: relative;
    margin: 50px 0;
    z-index: -1;
    .bg{
        position: absolute;
        width: 102%;
        left: -1%;
        top: 50%;
        transform: translateY(-50%);
        z-index: -1;
    }
    .container-main{
        position: relative;
        z-index: 1;
        .text-card{
            aspect-ratio: 0.8;
            display: flex;
            justify-content: center;
            align-items: center;
            .card-inner{
                font-size: 22px;
                font-weight: 600;
                display: block;
                max-width: 140px;
            }
        }
        .img-container{
            position: relative;
            margin: 50px 0;
            .circle{
                position: absolute;
                z-index: -1;
                &.circle1{
                    top: 24%;
                    left: 0;
                    transform: translateX(-50%);
                }
                &.circle2{
                    top: 50%;
                    left: 0;
                    transform: translateX(-160%);
                }
                &.circle3{
                    top: 10%;
                    right: 0;
                    transform: translateX(22%);
                }
                &.circle4{
                    bottom: 0;
                    left: 44%;
                }
            }
        }
    }
    .content-main{
        display: flex;
        justify-content: center;
        .content-inner{
            max-width: 250px;
            h2{
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

        @media screen and (max-width:959px){
            .content-inner{
                max-width: 400px;
                margin: 0 auto;
                text-align: center;
                h2{
                    font-size: 28px;
                    text-align: center;
                }
                .body{
                    text-align: center;
                }
            }
        }
    }
}
</style>
