<template>
  <div class="container">
    <marcatitulo titulo="Siemens" imagen="https://blog.mechatronik-group.com/wp-content/uploads/2020/04/p_d011_xx_00751p.png"></marcatitulo>
    <div class="preludio">
      <div class="una-columna">
        <div class="identidad">
          <img class="neugart-background" src="@/assets/RECURSOS GRAFICOS\otros\neugart-background.png">
          <img class="neugart-logo" src="@/assets/images/marcas/siemens.png">
        </div>
      </div>
      <div class="doble-columna">
        <div class="acerca">
          <p>Siemens está convirtiendo las ideas en innovaciones ganadoras que
            establecen nuevos estándares. Un ejemplo actual es la transición a
            una nueva combinación de energía: los nuevos métodos de simulación
            muestran cómo esto puede convertirse en una realidad y por qué los
            enfoques anteriores deben reconsiderarse.
            <br>
            <br>
            Ya sea síncrono o asíncrono, con o sin reductores, cuando se trata de
            seleccionar el motor óptimo para su aplicación de control de movimiento,
            Siemens tiene la selección de motores más amplia del mundo, que también
            cubre motores integrados y husillos de motor. Además, cada motor Siemens
            para control de movimiento está perfectamente adaptado para funcionar
            con nuestra familia de convertidores de frecuencia
          </p>
          <img class="clear" src="https://blog.mechatronik-group.com/wp-content/uploads/2020/01/simens1.jpg" alt="Servomotor">
        </div>
        <div class="acerca">
          <iframe width="560" height="315" src="https://www.youtube.com/embed/CsMDvpBfttc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      </div>
    </div>
    <marcacontent>
      <nuxt-link class="brand-title" to="/categorias/servomotors">
        <h2>Servomotores</h2>
      </nuxt-link>
      <p class="brand-paragraph">Los servomotores de rotación continua se caracterizan
        por ser capaces de girar 360 grados, es decir, una rotación completa.
        Su funcionamiento es similar al de un motor convencional,
        pero con las características de porder controlar su posición y velocidad de giro en un momento dado.</p>
      <relacionados categoria="37" cantidad="8"/>
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
