<template>
  <div class="container">
    <display v-if="categoriaId != null " :Modo='2' :categoriaId='categoriaId' :key='categoriaId'/>
  </div>
</template>

<script>
import display from '~/layouts/products/searcher.vue'

export default {
  components: {
    display
  },
  data: function() {
    return {
      categoriaId: 0
    }
  },
  mounted: async function() {
    var consulta = 'https://blog.mechatronik-group.com/wp-json/wc/v3/products/categories?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&slug=';
    consulta = consulta.concat(this.$route.params.catslug);
    var CategoriesId = await this.$axios.get(consulta);
    this.categoriaId = CategoriesId.data[0].id;
    console.log(this.categoriaId);
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
