<template>
  <div class="container">
    <marcatitulo titulo="Neugart" imagen="https://blog.mechatronik-group.com/wp-content/uploads/2020/04/neugart.png"></marcatitulo>
    <marcacontent>
      <nuxt-link class="brand-title" to="/categorias/planetary-gearbox">
        <h2>Planetary Gearbox</h2>
      </nuxt-link>
      <p class="brand-paragraph">La caja de engranajes planetarios con eje de
        salida suave es el elemento ideal para lograr una conexión de ajuste
        forzado a un acoplamiento. Esto le permite alcanzar la transmisión de par máximo incluso en modo inverso. </p>
      <relacionados :categoria="20" cantidad="8"/>
      <nuxt-link class="brand-title rigth" to="/categorias/planetary-gearbox">Ver Más &#10095 </nuxt-link>
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
