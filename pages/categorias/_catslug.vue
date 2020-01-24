<template>
  <div class="container">
    <display v-if="categoriaId != null " :Modo='2' :categoriaId='categoriaId' :categoriaNombre='categoriaNombre' :categoriaDescripcion='categoriaDescripcion' :key='categoriaId'/>
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
      categoriaId: 0,
      categoriaNombre: '',
      categoriaDescripcion: ''
    }
  },
  mounted: async function() {
    var consulta = 'https://blog.mechatronik-group.com/wp-json/wc/v3/products/categories?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&slug=';
    consulta = consulta.concat(this.$route.params.catslug);
    var CategoriesData = await this.$axios.get(consulta);
    this.categoriaNombre = CategoriesData.data[0].name;
    this.categoriaDescripcion = CategoriesData.data[0].description;
    this.categoriaId = CategoriesData.data[0].id;
    console.log(this.categoriaId);
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
