<template>
  <div class="container">
    <marcatitulo titulo="R+W" imagen="https://blog.mechatronik-group.com/wp-content/uploads/2020/04/rw.png"></marcatitulo>
    <div class="preludio">
      <div class="una-columna">
        <div class="identidad">
          <img class="neugart-background" src="@/assets/RECURSOS GRAFICOS\otros\rw-bg.png">
          <img class="neugart-logo" src="@/assets/images/marcas/RW_logo.svg">
        </div>
      </div>
      <div class="doble-columna">
        <div class="acerca">
          <p>Como fabricante de acoplamientos de precisión y ejes de línea,
            R + W presta servicios a clientes en todas las áreas relacionadas
            con la transmisión de energía. Establecida en 1990, R + W
            Antriebselemente GmbH emplea a más de 230 personas en todo el mundo.
            Esto incluye filiales en EE. UU., China, Italia y Eslovaquia, así
            como una oficina de ventas en Singapur. Además, R + W puede confiar en una red de distribuidores autorizados en más de 60 países.
            <br>
            <br>
            Los productos R + W se utilizan en una amplia variedad de industrias
            que requieren precisión absoluta y durabilidad confiable.
            Para adaptarse a la amplia gama de requisitos del cliente para soluciones
            individualizadas, los técnicos e ingenieros de R + W trabajan constantemente en el
            desarrollo de nuevos productos y en la mejora de los existentes. En el corazón del
            trabajo de desarrollo en R + W se encuentran los innovadores sistemas de acoplamiento
            para las muchas áreas de la tecnología de accionamiento.
          </p>
          <img class="clear" src="https://blog.mechatronik-group.com/wp-content/uploads/2020/01/bild_02-e1579911741896.jpg" alt="Coupling">
        </div>
        <div class="acerca">
          <iframe width="560" height="315" src="https://www.youtube.com/embed/X-vo09-93zw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      </div>
    </div>
    <marcacontent>
      <nuxt-link class="brand-title" to="/categorias/couplings">
        <h2>Couplings</h2>
      </nuxt-link>
      <p class="brand-paragraph">Un acoplamiento es un dispositivo utilizado para
        conectar dos ejes juntos en sus extremos con el fin de transmitir potencia.
        El propósito principal de los acoplamientos es unir dos piezas de equipo
        rotativo mientras permite cierto grado de desalineación o movimiento final o ambos.</p>
      <relacionados categoria="36" cantidad="4"/>
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

  .preludio {
    width: 90%;
      @media (min-width: 800px) {
      width: 80%;
    }
  }

  .doble-columna {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-column-gap: 50px;
    margin: 30px;
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
      width: 100%;
      max-width: 700px;
    }
  }

  .acerca {
    display: flex;
    justify-content: center;
    align-items:center;
    position: relative;
    p {
      text-align: justify;
    }
    .clear {
      display: block;
      height: 100%;
      position: absolute;
      opacity: 0.2;
    }
  }
</style>
