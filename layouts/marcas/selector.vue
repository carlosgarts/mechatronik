<template>
  <div>
  <loading v-if="marcas == undefined"/>
  <div v-else>
    <div class="selector">
     <transition-group name="fade" tag="div">
       <div v-for="i in [currentIndex]" :key="i">
         <div class="frame">
           <div class="content">
             <div class="marca">
               <img class="prod-logo" :src="currentSlide.logo" alt="neugart">
               <h4>Brand <strong>Overview</strong></h4>
             </div>
             <p>
               {{currentSlide.descripcion}} ssdvv dfe sdfs eeeeferer  Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
             </p>
             <a href="#" class="buttom-link" v-scroll-to="'#product--lister'">Ver productos</a>
           </div>
           <div class="side-tag"> <span>&#9472&#9472&#9472</span> {{currentSlide.titulo}}</div>
         </div>
         <img class="background-img" :src="currentSlide.imagen" />
       </div>
     </transition-group>
     <a class="prev" @click="prev" href="#">&#10094;</a>
     <a class="next" @click="next" href="#">&#10095;</a>
   </div>
   <lister porMarca="si" :Marca="currentSlide.titulo" :size="8" :idQuery="currentSlide.id" :key="currentIndex"/>
  </div>
  </div>
</template>

<script>
import lister from '../products/lister.vue'
import loading from '../partials/loading.vue'

export default {
  components: {
    lister,
    loading
  },
  data: function() {
    return {
      marcas: null,
      timer: null,
      currentIndex: 0,
      isLoading: true
    }
  },
  methods: {
    startSlide: function() {
      // this.timer = setInterval(this.next, 15000);
    },
    next: function() {
      this.currentIndex += 1;
    },
    prev: function() {
      this.currentIndex -= 1;
    }
  },
  computed: {
    currentSlide: function() {
      return this.marcas[Math.abs(this.currentIndex) % this.marcas.length];
    }
  },
  beforeMount: async function() {
      try {
        var Marca = await this.$axios.get('http://mechatronik-group.com:4000/api/marcas');
        this.marcas = Marca.data.marcas;
        this.isLoading = false;
      } catch (e) {
        this.isLoading = false;
        console.log(e);
      }
    this.startSlide();
  }
}
</script>

<style lang="scss" scoped>
@import "../../assets/css/selector.scss";
</style>
