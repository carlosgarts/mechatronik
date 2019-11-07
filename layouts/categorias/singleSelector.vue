<template>
  <div>
    <error v-if="categorias == undefined"/>
    <div  v-else>
      <div class="selector">
       <transition-group name="fade" tag="div">
         <div v-for="i in [currentIndex]" :key="i">
           <div class="frame">
             <div class="content">
               <div class="marca">
                 <h4>{{categorias.titulo}}</h4>
               </div>
               <p v-html="categorias.descripcion"></p>
               <a href="#" class="buttom-link" v-scroll-to="'#product--lister'">Ver productos</a>
             </div>
             <div class="side-tag"> <span>&#9472&#9472&#9472</span> Marcas</div>
           </div>
           <img class="background-img" :src="categorias.imagen" />
         </div>
       </transition-group>
     </div>
     <lister porMarca="no" :Categoria="categorias.titulo" :size="8":idQuery="categorias.id" :key="currentIndex"/>
    </div>
  </div>
</template>

<script>
import lister from '../products/lister.vue'
import error from '../partials/error.vue'

export default {
  components: {
    lister,
    error
  },
  data: function() {
    return {
      categorias: {},
      timer: null,
      currentIndex: 0,
      isLoading: true
    }
  },
  mounted: async function() {
      try {
        const id = this.$route.params.id;
        var consulta = 'https://system.mechatronik-group.com/api/categorias/',
        consulta = consulta.concat(id);
        var Category = await this.$axios.get(consulta);
        this.categorias = Category.data.categorias[0];
        this.isLoading = false;
      } catch (e) {
        this.isLoading = false;
        console.log(e);
      }
  }
}
</script>

<style lang="scss" scoped>
@import "../../assets/css/selector.scss";
</style>
