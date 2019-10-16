<template>
  <div class="container">
    <Intro1/>
    <Intro2/>
  </div>
</template>

<script>
import Intro1 from '~/layouts/products/intro1.vue'
import Intro2 from '~/layouts/products/intro2.vue'

export default {
  components: {
    Intro1,
    Intro2
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: #f0f6f7;
  }
</style>
