<script setup>
import Header from "./../components/default/header.vue"
import Footer from "./../components/default/footer.vue"

import Welcome from "./../components/blocks/welcome.vue"
import Services from "./../components/blocks/services.vue"
import Campaign from "./../components/blocks/campaign.vue"
import Plumbing from "./../components/blocks/plumbing.vue"
import Problems from "./../components/blocks/problems.vue"
import Service from "./../components/blocks/service.vue"
import Faq from "./../components/blocks/faq.vue"
import Contact from "./../components/blocks/contact.vue"
import About from './../components/blocks/about.vue'
import About2 from './../components/blocks/about2.vue'
import About3 from './../components/blocks/about3.vue'


</script>

<template>
    <section id="main">
      <Header />
      
      <Welcome />

      <Services />

      <Campaign />

      <Plumbing />

      <Problems />

      <Service />

      <Faq />

      <Contact />

      <About />
      
      <About2 />

      <About3 />


      <Footer />
    </section>
</template>

<style scoped lang="scss">
  
  #main {
      position: relative;
      z-index: 3;
      overflow: hidden;
  }
</style>
