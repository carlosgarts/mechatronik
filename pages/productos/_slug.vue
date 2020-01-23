<template>
  <div class="container">
    <display :Modo='1'/>
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
