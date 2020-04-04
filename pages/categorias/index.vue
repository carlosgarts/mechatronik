<template>
  <div class="container">
    <categoriesHeader/>
    <categories/>
    <categoriesFooter/>
  </div>
</template>

<script>
import categoriesHeader from '~/layouts/products/categorias-header.vue'
import categories from '~/layouts/products/categories.vue'
import categoriesFooter from '~/layouts/products/categorias-footer.vue'

export default {
  components: {
    categoriesHeader,
    categories,
    categoriesFooter
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
