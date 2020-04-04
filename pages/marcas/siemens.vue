<template>
  <div class="container">
    <marcatitulo titulo="Siemens" imagen="https://blog.mechatronik-group.com/wp-content/uploads/2020/04/p_d011_xx_00751p.png"></marcatitulo>
    <marcacontent>
      <nuxt-link class="brand-title" to="/categorias/servomotors">
        <h2>Servomotores</h2>
      </nuxt-link>
      <p class="brand-paragraph">Los servomotores de rotación continua se caracterizan
        por ser capaces de girar 360 grados, es decir, una rotación completa.
        Su funcionamiento es similar al de un motor convencional,
        pero con las características de porder controlar su posición y velocidad de giro en un momento dado.</p>
      <relacionados :categoria="20" cantidad="8"/>
      <nuxt-link class="brand-title rigth" to="/categorias/servomotors">Ver Más &#10095 </nuxt-link>
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
