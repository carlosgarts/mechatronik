<template>
  <div class="container">
    <companyHeader/>
    <Mision/>
  </div>
</template>

<script>
// import About from '~/layouts/company/about.vue'
import companyHeader from '~/layouts/company/company-header.vue'
import Mision from '~/layouts/company/mision.vue'

export default {
  components: {
    Mision,
    companyHeader
  }
}
</script>

<style lang="scss" scoped>
  .container {
    //padding-top: 100px;
    background-color: #f0f6f7;
  }
</style>
