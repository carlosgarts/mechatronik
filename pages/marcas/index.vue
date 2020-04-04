<template>
  <div class="container">
    <marcasheader/>
    <marcas/>
    <marcasfooter/>
  </div>
</template>

<script>
import marcasheader from '~/layouts/marcas/marcas-header.vue'
import marcas from '~/layouts/marcas/marcas.vue'
import marcasfooter from '~/layouts/marcas/marcas-footer.vue'

export default {
  components: {
    marcasheader,
    marcas,
    marcasfooter
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
