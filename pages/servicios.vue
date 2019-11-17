<template>
  <div class="container">
    <SolucionesHeader/>
    <Servicios/>
    <SolucionesFooter/>
  </div>
</template>

<script>
import SolucionesHeader from '~/layouts/servicios/servicios-header.vue'
import Servicios from '~/layouts/servicios/servicios.vue'
import SolucionesFooter from '~/layouts/servicios/servicios-footer.vue'

export default {
  components: {
    SolucionesHeader,
    Servicios,
    SolucionesFooter
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
