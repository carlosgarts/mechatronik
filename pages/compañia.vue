<template>
  <div class="container">
    <About/>
    <Mision/>
  </div>
</template>

<script>
import About from '~/layouts/company/about.vue'
import Mision from '~/layouts/company/mision.vue'

export default {
  components: {
    About,
    Mision
  }
}
</script>

<style lang="scss" scoped>
  .container {
    //padding-top: 100px;
    background-color: #f0f6f7;
  }
</style>
