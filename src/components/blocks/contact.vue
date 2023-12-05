<script setup>

</script>

<template>
  <section class="contact-main" id="contact">
    <v-container>
      <div class="d-flex justify-center">
        <h2 class="section-title mb-6">İletişim</h2>
      </div>
      <div class="d-flex justify-center">
        <VList density="compact" class="mb-3">
          <VListItem
            href="tel:+905523343071"
            prepend-icon="mdi-phone"
          >
            +90 (552) 334 30 71
          </VListItem>
          <VListItem
            href="mailto:info@cayyolutesisatcisi.com"
            prepend-icon="mdi-mail"
          >
            info@cayyolutesisatcisi.com
          </VListItem>
        </VList>
      </div>
      <div>
        <iframe width="100%" height="500" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" src="https://maps.google.com/maps?width=100%25&amp;height=600&amp;hl=en&amp;q=39.8863279,32.6952527+(%C3%87ayyolu%20Tesisat%C3%A7%C4%B1s%C4%B1)&amp;t=&amp;z=13&amp;ie=UTF8&amp;iwloc=B&amp;output=embed"></iframe>
      </div>
    </v-container>
    
  </section>
</template>

<style lang="scss">
.contact-main{
    padding: 0 0 50px 0;
    .section-title{
        font-size: 36px;
    }
}
</style>
