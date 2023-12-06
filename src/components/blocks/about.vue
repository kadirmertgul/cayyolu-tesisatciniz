<script setup>

const title = 'Çayyolu Su Tesisatı'

const body = 'Çayyolu su tesisatı firması olarak yakın zamanda hizmete girmiş olan, sektörde çok hızlı büyüyen çayyolu su tesisatı firmamız ile evinde problem yaşayan ev sahiplerine çayyolu genelinde hızlı, güvenli, hesaplı ve kaliteli su tesisatı hizmeti sağlamaktayız. Hem güm içinde hem de gece acil durumlarda günün her saati bizleri arayabilirsiniz. Ev sahipleri kalorifer, kombi , sıcak su, su kaçağı ve benzeri durumlar yaşayabilmektedir. Bu zor zamanınızı sorunsuz atlatmanız için destek veren çayyolu su tesisatı, en kaliteli hizmeti sunmak için 7 gün 24 saat, yardıma ihtiyaç duyduğunuz her an sizlerin yanında olmaktadır. '

</script>

<template>
    <section class="about-main">
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
        }
    }
</style>
