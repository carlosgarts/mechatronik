<template>
  <div class="container">
    <marcatitulo titulo="R+W" imagen="https://blog.mechatronik-group.com/wp-content/uploads/2020/04/rw.png"></marcatitulo>
    <marcacontent>
      <nuxt-link class="brand-title" to="/categorias/couplings">
        <h2>Couplings</h2>
      </nuxt-link>
      <p class="brand-paragraph">Un acoplamiento es un dispositivo utilizado para
        conectar dos ejes juntos en sus extremos con el fin de transmitir potencia.
        El propósito principal de los acoplamientos es unir dos piezas de equipo
        rotativo mientras permite cierto grado de desalineación o movimiento final o ambos.</p>
      <relacionados :categoria="36" cantidad="4"/>
      <nuxt-link class="brand-title rigth" to="/categorias/couplings">Ver Más &#10095 </nuxt-link>
      <!-- <hr> -->
    </marcacontent>
  </div>
</template>

<script>
import marcatitulo from '~/layouts/marcas/marcas-displayer-header.vue'
import marcacontent from '~/layouts/marcas/marcas-displayer.vue'
import relacionados from '~/layouts/partials/widgets/productos.vue'

export default {
  components: {
    marcatitulo,
    marcacontent,
    relacionados
  },
  data: function() {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
  .brand-paragraph {
    line-height: 1.6;
  }
  .brand-title {
    text-decoration: none;
    color: #65A3AE;
    &.right {

    }
    h2 {
      margin: 0;
      font-size: calc(35px + (45 - 35) * ((100vw - 300px) / (1600 - 300)));
      font-style: normal;
      font-weight: normal;
      font-family: 'OpenSans', Fallback, sans-serif;
    }
  }

  hr {
    border: none;
    border-top: 1px solid gray;
    margin: 30px 0;
  }
</style>
