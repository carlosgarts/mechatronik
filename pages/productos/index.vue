<template>
  <div class="searcher-container">
    <Searcher :Modo='1'/>
  </div>
</template>

<script>
import Searcher from '~/layouts/products/searcher.vue'

export default {
  components: {
    Searcher
  }
}
</script>

<style lang="scss" scoped>
  .searcher-container {
    background-color: #FFFFFF;
    width: 100%;
  }
</style>
