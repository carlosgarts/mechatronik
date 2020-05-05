<template>
  <div class="container">
    <marcatitulo titulo="Neugart" imagen="https://blog.mechatronik-group.com/wp-content/uploads/2020/04/neugart.png"></marcatitulo>
    <div class="preludio">
      <div class="una-columna">
        <div class="identidad">
          <img class="neugart-background" src="@/assets/images/recursos/bg-helix.png">
          <img class="neugart-logo" src="@/assets/images/marcas/neugart.png">
        </div>
      </div>
      <div class="doble-columna">
        <div class="acerca">
          <p>Neugart es una empresa familiar entre los fabricantes de cajas de
            cambios. Fundada en 1928, Neugart permanece en manos de la familia,
            ahora en la cuarta generación. Neugart desarrolla,
            produce y vende cajas de cambios planetarias y cajas de cambios personalizadas.
            La compañía emplea a más de 700 personas en todo el mundo,
            incluidas más de 600 en su sede en Kippenheim, en el suroeste de Alemania.
            <br>
            <br>
            Durante medio siglo, Neugart ha estado desarrollando y produciendo cajas de engranajes planetarios adaptadas a estos requisitos. Desde entonces, hemos seguido mejorando nuestros productos en cooperación con nuestros clientes.
            <br>
            <br>
            Una caja de cambios debe cumplir los requisitos más diversos dictados por el tipo de aplicación. Las aplicaciones de manejo lineal altamente dinámicas exigen componentes robustos y de alto rendimiento. Gracias a los bajos pesos de los componentes del variador, los sistemas de ejes múltiples logran un efecto de regulación positivo y, por lo tanto, tiempos de rendimiento más eficientes. Por otro lado, los sistemas de selección y colocación exigen una alta repetibilidad y una rigidez del sistema correspondiente que promueva la colocación rápida y precisa.
            <br>
            <br>
            Las cajas de engranajes planetarios Neugart se pueden configurar individualmente según los requisitos. Funcionan de manera confiable y precisa y cumplen con los requisitos de nuestros clientes, sin importar cuán exigentes sean.
          </p>
          <img class="clear" src="https://blog.mechatronik-group.com/wp-content/uploads/2020/01/PLHE_01_RGB_JPEG.jpg" alt="Servomotor">
        </div>
        <div class="acerca">
          <iframe width="560" height="315" src="https://www.youtube.com/embed/ckG6B7WcKIU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      </div>
    </div>
    <marcacontent>
      <nuxt-link class="brand-title" to="/categorias/planetary-gearbox">
        <h2>Planetary Gearbox</h2>
      </nuxt-link>
      <p class="brand-paragraph">La caja de engranajes planetarios con eje de
        salida suave es el elemento ideal para lograr una conexión de ajuste
        forzado a un acoplamiento. Esto le permite alcanzar la transmisión de par máximo incluso en modo inverso. </p>
      <relacionados categoria="20" cantidad="8"/>
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
      max-width: 350px;
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
