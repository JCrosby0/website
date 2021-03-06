<template>
  <div class="page-layout">
    <Header class="header" />
    <div class="section section-default">
      <div class="container container-large">
        <Nuxt />
      </div>
    </div>
  </div>
</template>

<script>
// Import your new Header component
import Header from '~/components/Header.vue'
export default {
  components: {
    Header,
  },
}
</script>

<style></style>
