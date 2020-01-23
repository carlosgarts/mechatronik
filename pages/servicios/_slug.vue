<template>
  <div class="container">
      <ServiciosReader/>
  </div>
</template>

<script>
import ServiciosReader from '~/layouts/servicios/servicios-reader.vue'

export default {
  components: {
    ServiciosReader
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
