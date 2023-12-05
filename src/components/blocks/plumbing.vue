<script setup>
import dots from '../../assets/dots.svg'
import plumbing1 from '../../assets/img/plumbing/plumbing-1.png'
import plumbing2 from '../../assets/img/plumbing/plumbing-2.png'
import plumbing3 from '../../assets/img/plumbing/plumbing-3.png'
import plumbing4 from '../../assets/img/plumbing/plumbing-4.png'

const title = 'Sıhhi Tesisat'
const body = 'Sıhhi tesisat evin can damarıdır. Evin damarlarındaki en ufak bir aksama size yüklü maliyetler doğurabilir.'

</script>

<template>
  <section class="plumbing-main">
    <v-container>
      <VRow>
        <VCol cols="12" md="5" class="d-flex align-center content-main">
          <div class="content-inner">
            <h2>{{ title }}</h2>
            <div class="body" v-html="body"></div>
            <VBtn
              color="warning"
              size="large"
              href="tel:+905523343071"
              style="text-transform: none; font-size: 13px;"
            >
              Hemen Ara
            </VBtn>
          </div>
        </VCol>
        <VCol cols="11" md="7" lg="6" xl="5" class="img-container">
          <img :src="dots" class="dots" />
          <VRow>
            <VCol cols="6" class="pt-12">
              <VImg :src="plumbing1" class="mb-6" />
              <VImg :src="plumbing2" />
            </VCol>
            <VCol cols="6">
              <VImg :src="plumbing3" class="mb-6" />
              <VImg :src="plumbing4" />
            </VCol>
          </VRow>
        </VCol>
      </VRow>
    </v-container>
  </section>
</template>

<style lang="scss">
.plumbing-main{
    margin-top: 50px;
    margin-bottom: 50px;
    .img-container{
        position: relative;
        margin: 50px 0;
        .dots{
            position: absolute;
            top: 50%;
            right: 0;
            z-index: -1;
            transform: translateY(-48%) scale(80%) translateX(40px);
        }
    }
    .content-main{
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
