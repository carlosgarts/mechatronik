<template>
  <div class="container">
    <display/>
  </div>
</template>

<script>
import display from '~/layouts/products/display.vue'

export default {
  components: {
    display
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
