<template>
  <div class="container">
    <marcatitulo titulo="Festo" imagen="https://blog.mechatronik-group.com/wp-content/uploads/2020/04/neugart.png"></marcatitulo>
    <div class="preludio">
      <div class="una-columna">
        <div class="identidad">
          <img class="neugart-background" src="@/assets/RECURSOS GRAFICOS\otros\festo-bg.png">
          <img class="neugart-logo" src="@/assets/images/marcas/festo.png">
        </div>
      </div>
      <div class="doble-columna">
        <div class="acerca">
          <p>
            Festo es una empresa multinacional alemana de control y automatización
            industrial con sede en Esslingen am Neckar, Alemania. Festo es una empresa
            impulsada por la ingeniería, que produce y vende tecnología de control y
            accionamiento neumático y eléctrico para la automatización de fábricas o procesos.
            Festo Didactic es líder mundial en educación y consultoría industrial y es socio
            patrocinador fundador de WorldSkills Mechatronics Competitions. Las filiales de ventas,
            los centros de distribución y las fábricas se encuentran en 61 países de todo el mundo.
            La compañía lleva el nombre de sus fundadores Albert Fezer y Gottlieb Stoll.
          </p>
          <!-- <img class="clear" src="https://blog.mechatronik-group.com/wp-content/uploads/2020/01/bild_02-e1579911741896.jpg" alt="Coupling"> -->
        </div>
        <div class="acerca">
          <iframe width="560" height="315" src="https://www.youtube.com/embed/eJSUHxS0Xz4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      </div>
    </div>
    <marcacontent>
      <!-- <nuxt-link class="brand-title" to="/categorias/planetary-gearbox">
        <h2>Planetary Gearbox</h2>
      </nuxt-link>
      <p class="brand-paragraph">La caja de engranajes planetarios con eje de
        salida suave es el elemento ideal para lograr una conexión de ajuste
        forzado a un acoplamiento. Esto le permite alcanzar la transmisión de par máximo incluso en modo inverso. </p>
      <relacionados categoria="20" cantidad="8"/>
      <nuxt-link class="brand-title rigth" to="/categorias/planetary-gearbox">Ver Más &#10095 </nuxt-link> -->
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
      max-width: 500px;
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
