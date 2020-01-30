<template>
  <div class="container">
    <ServiciosHeader/>
    <Servicios/>
    <ServiciosFooter/>
  </div>
</template>

<script>
import ServiciosHeader from '~/layouts/servicios/servicios-header.vue'
import Servicios from '~/layouts/servicios/servicios.vue'
import ServiciosFooter from '~/layouts/servicios/servicios-footer.vue'

export default {
  components: {
    ServiciosHeader,
    Servicios,
    ServiciosFooter
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
