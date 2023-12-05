<script setup>

const menuTitles = {
    main: 'Çayyolu Tesisatçınız',
    menu1: 'Tüm Linkler',
    menu2: 'İçindekiler',
    social: 'Sosyal Medya',
}
const mainBody = 'Tüm Hakları Saklıdır.'

const menu1 = [
    {
        title: 'Web Tasarım',
        href: 'https://www.google.com'
    },
    {
        title: 'Mobil Uygulama',
        href: 'https://www.google.com'
    },
    {
        title: 'SEO Optimizasyonu',
        href: 'https://www.google.com'
    },
    {
        title: 'Sosyal Medya',
        href: 'https://www.google.com'
    },
]
const menu2 = [
    {
        title: 'Anasayfa',
        href: '#home'
    },
    {
        title: 'Hizmetler',
        href: '#services'
    },
    {
        title: 'İletişim',
        href: '#contact'
    },
]

const social = [
    {
        icon: 'mdi-facebook',
        href: 'https://www.facebook.com'
    },
    {
        icon: 'mdi-twitter',
        href: 'https://www.twitter.com'
    },
    {
        icon: 'mdi-youtube',
        href: 'https://www.youtube.com'
    },
    {
        icon: 'mdi-instagram',
        href: 'https://www.instagram.com'
    },
]

</script>

<template>
    <VFooter color="warning" class="py-12 footer-main">
      <VContainer>
        <VRow>
          <VCol cols="12" md="3">
            <h3>{{ menuTitles.main }}</h3>
            <div v-html="mainBody" class="pt-3"></div>
          </VCol>
          <VCol cols="12" md="3">
            <h4>{{ menuTitles.menu1 }}</h4>
            <VList density="compact" bg-color="warning">
              <VListItem
                v-for="(item, key) in menu1"
                :key="key"
                :href="item.href"
                class="ps-0 menu-item"
              >
                {{ item.title }}
              </VListItem>
            </VList>
          </VCol>
          <VCol cols="12" md="3">
            <h4>{{ menuTitles.menu2 }}</h4>
            <VList density="compact" bg-color="warning">
              <VListItem
                v-for="(item, key) in menu2"
                :key="key"
                :href="item.href"
                class="ps-0 menu-item"
              >
                {{ item.title }}
              </VListItem>
            </VList>
          </VCol>
          <VCol cols="12" md="3">
            <h4>{{ menuTitles.social }}</h4>
            <div class="d-flex pt-3 ga-2">
              <a
                v-for="(item, key) in social"
                :key="key"
                :href="item.href"
              >
                <VIcon :icon="item.icon" />
              </a>
            </div>
          </VCol>
        </VRow>
      </VContainer>
    </VFooter>
</template>

<style lang="scss">
  .footer-main{
      *{
          color: #242424;
      }
      .menu-item{
          font-size: 14px;
      }
  }
</style>
