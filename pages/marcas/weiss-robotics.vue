<template>
  <div class="container">
    <marcatitulo titulo="Weiss Robotics" imagen="https://blog.mechatronik-group.com/wp-content/uploads/2020/04/neugart.png"></marcatitulo>
    <div class="preludio">
      <div class="una-columna">
        <div class="identidad">
          <!-- <img class="neugart-background" src="@/assets/images/recursos/neugart-background.png"> -->
          <img class="neugart-logo" src="@/assets/images/marcas/weiss.png">
        </div>
      </div>
      <div class="doble-columna">
        <div class="acerca">
          <p>Fundada en 2008 como una startup, hoy somos el especialista líder en
            sistemas de agarre mecatrónico. Como empresa familiar administrada por el propietario,
            desarrollamos soluciones de agarre innovadoras para tareas de automatización exigentes
            en nuestra sede en Ludwigsburg, Alemania, estableciendo nuevos estándares tanto cualitativa
            como tecnológicamente en el contexto de la Industria 4.0 y la Fábrica inteligente.
          </p>
          <img class="clear" src="https://blog.mechatronik-group.com/wp-content/uploads/2020/02/product-picture.jpg" alt="Servomotor">
        </div>
        <div class="acerca">
          <iframe width="560" height="315" src="https://www.youtube.com/embed/HgcfaYy2O4w" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      </div>
    </div>
    <marcacontent>
      <nuxt-link class="brand-title" to="/categorias/grippers">
        <h2>Grippers</h2>
      </nuxt-link>
      <p class="brand-paragraph">Desarrollamos soluciones de agarre innovadoras
        para tareas de automatización exigentes, que establecen nuevos estándares
        en términos de tecnología y tecnología en el contexto de la Industria 4.0 y
        la Fábrica inteligente. </p>
      <relacionados categoria="40" cantidad="8"/>
      <nuxt-link class="brand-title rigth" to="/categorias/grippers">Ver Más &#10095 </nuxt-link>
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

  .preludio {
    width: 90%;
      @media (min-width: 800px) {
      width: 80%;
    }
  }

  .doble-columna {
    display: grid;
    grid-template-columns: 1fr;
    grid-column-gap: 50px;
    margin: 30px;
    @media (min-width: 1150px) {
      grid-template-columns: 1fr 1fr;
    }
  }

  .una-columna {
    display: grid;
    grid-template-columns: 1fr;
    grid-column-gap: 50px;
    margin: 30px;
    height: 30vh;
  }

  .identidad {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    img {
      width: 100%;
    }
    .neugart-logo {
      position: absolute;
      z-index: 15;
      max-width: 500px;
    }
    .neugart-background {
      position: absolute;
      max-width: 100%;
    }
  }

  .acerca {
    display: flex;
    justify-content: center;
    align-items:center;
    position: relative;
    width: 100%;
    p {
      text-align: justify;
    }
    .clear {
      display: block;
      height: 100%;
      width: 100%;
      object-fit: contain;
      position: absolute;
      opacity: 0.2;
    }
  }

  iframe {
    width: 100%;
  }
</style>
