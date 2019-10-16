<template>
  <div class="container">
    <Selector/>
  </div>
</template>

<script>
import Selector from '~/layouts/marcas/selector.vue'

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
