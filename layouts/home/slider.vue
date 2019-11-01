<template>
  <div class="section">
    <div id="slider--intro">
      <carousel class="carrousel" :perPage="1" :paginationEnabled="true" paginationActiveColor="#65A3AE" :autoplay="true" :autoplayTimeout="5000" :autoplayHoverPause="false" :loop="true">
        <slide v-bind:id="information.id"  class="slide" v-for="information in informations" v-bind:key="information.id">
          <div class="tbb">
            <h2 v-html="information.title"></h2>
          </div>
          <p v-html="information.content"></p>
        </slide>
      </carousel>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      informations: {
        0: {
          id: "slide--1",
          title:"Nuestra <strong>experiencia</strong>",
          content: "Desarrollamos proyectos llave en mano enfocados en la automatización de sus procesos de manufactura, somos una empresa dedicada al diseño e integración de soluciones orientadas a la Industria 4.0. <br> <br> Nuestro enfoque se adapta a las necesidades específicas de cada cliente y el sector donde se desempeña su negocio. <br> <br> Contamos con un amplio conjunto de servicios especializados, amplia experiencia en la ingeniería de automatización y gran capacidad diferencial para integrar nuevas tecnologías, lo que nos permite implantar mejoras de gran valor y acelerar los resultados con un impacto visible en el negocio."
        },
        1: {
          id: "slide--2",
          title:"Soluciones <strong>de Ingenieria</strong>",
          content: "La coordinación interdisciplinaria y en su mayoría global de los participantes en el proyecto es especialmente posible si los conocimientos existentes se comparten y coordinan a propósito. Para esto confiamos en herramientas comprobadas de planificación y análisis. Se coordinan la planificación de procesos y diseño, análisis y simulación de componentes, programación y análisis MTM. (Methods Time Measurement)"
        },
        2: {
          id: "slide--3",
          title:"Servicios a <strong>la medida</strong>",
          content: "Nuestros servicios a la medida siempre cumplen con la tecnología más avanzada y ofrece una excelente relación costo-beneficio Al mismo tiempo, utilizando diversas herramientas de cálculo, determinamos costos, viabilidad y planificación del proyecto. Para esto confiamos en herramientas comprobadas de planificación y análisis. Se coordinan la planificación de procesos y diseño, análisis y simulación de componentes, programación y análisis MTM."
        },
        3: {
          id: "slide--4",
          title:"Portafolio <strong>de productos</strong>",
          content: "Ya sea para un posicionamiento preciso y repetible, velocidad constante y alto movimiento dinámico, largas trayectorias de desplazamiento o cambios rápidos de velocidad – Tenemos una cartera de servos, reductores planetarios, actuadores lineales y más para la solución optima para cada tarea de control de movimiento"
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>

  .section {
    display: none;
    @media (min-width: 700px) {
      display: flex;
    }
  }

  .carrousel {
    height: 100vh;
    width: 100%;
  }

  #slide--1 {
    background: url('../../assets/images/Inicio/Banner-experiencia.jpg') no-repeat;
    background-size: cover;
  }
  #slide--2 {
    background: url('../../assets/images/Inicio/Banner-Soluciones.jpg') no-repeat;
    background-size: cover;
  }
  #slide--3 {
    background: url('../../assets/images/Inicio/Banner-Servicios.jpg') no-repeat;
    background-size: cover;
  }
  #slide--4 {
    background: url('../../assets/images/Inicio/Banner-productos.jpg') no-repeat;
    background-size: cover;
  }

  .slide {
    height: 100vh;
    width: 100%;
    background-size: cover;
    display: flex;
    justify-content: center;
    flex-flow: column;
    align-items: flex-start;
    text-align: left;
    color: white;
    p {
      width: 90%;
      margin-left: 5%;
      margin-right: 5%;
      font-size: 12px;
      line-height: 1.3;
      @media (min-width: 400px) {
        font-size: 1em;
      }
      @media (min-width: 600px) {
        width: 50%;
        margin-left: 10%;
      }
    }
  }

</style>
