<template>
  <div class="container">
    <ExitosHeader/>
    <Exitos/>
    <ExitosFooter/>
  </div>
</template>

<script>
import ExitosHeader from '~/layouts/exitos/exitos-header.vue'
import Exitos from '~/layouts/exitos/exitos.vue'
import ExitosFooter from '~/layouts/exitos/exitos-footer.vue'

export default {
  components: {
    ExitosHeader,
    Exitos,
    ExitosFooter
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
