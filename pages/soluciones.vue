<template>
  <div class="container">
      <SolucionesHeader/>
      <Soluciones/>
      <SolucionesFooter/>
  </div>
</template>

<script>
import SolucionesHeader from '~/layouts/soluciones/soluciones-header.vue'
import Soluciones from '~/layouts/soluciones/soluciones.vue'
import SolucionesFooter from '~/layouts/soluciones/soluciones-footer.vue'

export default {
  components: {
    SolucionesHeader,
    Soluciones,
    SolucionesFooter
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
