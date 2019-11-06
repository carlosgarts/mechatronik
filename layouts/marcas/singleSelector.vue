<template>
  <div>
  <error v-if="marcas == undefined"/>
  <div v-else>
    <div class="error" v-if="marcas == undefined">
      <h1>404</h1>
      <p>Disculpe pero esta pagina no existe</p>
    </div>
      <div  v-else>
      <div class="selector">
       <transition-group name="fade" tag="div">
         <div v-for="i in [currentIndex]" :key="i">
           <div class="frame">
             <div class="content">
               <div class="marca">
                 <img class="prod-logo" :src="marcas.logo" alt="neugart">
                 <h4>Brand <strong>Overview</strong></h4>
               </div>
               <p v-html="marcas.descripcion"></p>
               <a href="#" class="buttom-link" v-scroll-to="'#product--lister'">Ver productos</a>
             </div>
             <div class="side-tag"> <span>&#9472&#9472&#9472</span> {{marcas.titulo}}</div>
           </div>
           <img class="background-img" :src="marcas.imagen" />
           </div>
         </transition-group>
       </div>
       <lister porMarca="si" :Marca="marcas.titulo" :size="8" :idQuery="marcas.id" :key="currentIndex"/>
      </div>
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
      marcas: {},
      timer: null,
      currentIndex: 0,
      isLoading: true
    }
  },
  mounted: async function() {
      try {
        const id = this.$route.params.id;
        var consulta = 'http://mechatronik-group.com:4000/api/marcas/',
        consulta = consulta.concat(id);
        var Marca = await this.$axios.get(consulta, {
          params: {
            id: id
          }
        });
        this.marcas = Marca.data.marcas[0];
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
