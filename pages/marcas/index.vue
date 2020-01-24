<template>
  <div class="container">
    <display/>
  </div>
</template>

<script>
import display from '~/layouts/products/searcher.vue'

export default {
  components: {
    Selector
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
