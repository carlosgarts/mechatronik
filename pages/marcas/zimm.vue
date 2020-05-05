<template>
  <div class="container">
    <marcatitulo titulo="Zimm" imagen="https://blog.mechatronik-group.com/wp-content/uploads/2020/04/zimm4.jpg"></marcatitulo>
    <div class="preludio">
      <div class="una-columna">
        <div class="identidad">
          <img class="neugart-background" src="@/assets/RECURSOS GRAFICOS\otros\zimm-bg.png">
          <img class="neugart-logo" src="@/assets/images/marcas/zimm.png">
        </div>
      </div>
      <div class="doble-columna">
        <div class="acerca">
          <p>
            La innovación es una parte esencial de nuestro pensamiento y filosofía. Disponemos de un laboratorio de pruebas interno en el que se llevan a cabo diversas pruebas e investigaciones de nuestros productos. También colaboramos con reconocidos institutos de investigación y proveedores de servicios que complementan nuestro trabajo de desarrollo. De este modo obtenemos información importante y resultados de pruebas, que influyen directamente en la mejora de la calidad y confirman el desarrollo de nuestros productos en sus cálculos y declaraciones. <br>
            <br>
            <br>
            Además de la base de un grado de integración vertical de los componentes centrales del sistema modular, permitimos un nivel muy alto de disponibilidad a través de procesos de producción flexibles y un gran stock coordinado de componentes y productos terminados. Esto da como resultado unos tiempos de entrega cortos y puntuales para los productos estándar. Debido a las diversas y especiales instalaciones de producción, también podemos satisfacer los requisitos especiales de nuestros clientes.
          </p>
          <img class="clear" src="https://blog.mechatronik-group.com/wp-content/uploads/2020/01/ze-10kn-r-trapezoidal-screw-20x4-1-e1579912312687.png" alt="Servomotor">
        </div>
        <div class="acerca">
          <iframe width="560" height="315" src="https://www.youtube.com/embed/GvDFLSgEYxU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      </div>
    </div>
    <marcacontent>
      <nuxt-link class="brand-title" to="/categorias/screw-jack-system">
        <h2>Screw Jack System</h2>
      </nuxt-link>
      <p class="brand-paragraph">Los sistemas de gato de tornillo se utilizan en
        líneas de producción y montaje automatizadas. Una caja de engranajes de gato de
        tornillo es un accionamiento electromecánico y se utiliza donde los pesos deben
        controlarse con mucha precisión y colocarse con cuidado.
      </p>
      <relacionados categoria="38" cantidad="8"/>
      <nuxt-link class="brand-title rigth" to="/categorias/screw-jack-system">Ver Más &#10095 </nuxt-link>
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
