<template>
  <div class="section">
    <div id="soluciones--3">
      <div class="bar--picture" v-scroll-reveal.reset>
        <div class="tbb">
          <h2>CONSULTORÍA</h2>
        </div>
        <div class="content">
          <div class="text">
            <h4>Para la automatización <br> de la producción</h4>
            <p>Ya sea para un posicionamiento preciso y repetible, una velocidad constante y un movimiento dinámico alto, recorrido largos o cambios de velocidad rápidos, tenemos una cartera de servos, reductores planetarios, actuadores lineales y más para la solución óptima para cada tarea de control de movimiento. <br> <br> Esto simplifica la ingeniería y la puesta en servicio. Soluciones de sistema para aplicaciones de alto rendimiento.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>

.section {
  background-color: white;
  background: url('../../assets/images/Soluciones/Consultoria.jpg') no-repeat;
  background-size: cover;
}

#soluciones--3 {
  position: relative;
  .bar--picture {
    width: 100%;
    padding-top: 50vh;
    display: flex;
    flex-flow: column;
    align-items: flex-start;
    @media (min-width: 1000px) {
      width: 85%;
      padding-top: 25px;
    }
    .tbb {
      display: flex;
      h2 {
        padding-bottom: 15px;
        font-size: 45px;
        font-size: calc(20px + (60 - 20) * ((100vw - 300px) / (1600 - 300)));
        font-weight: bold;
      }
    }
    .content {
      margin-left: 7.5%;
      display: flex;
      @media (min-width: 1000px) {
        margin-left: 15%;
      }
    }
    .text {
      text-align: left;
      color: white;
      width: 85%;
      margin-bottom: 20vh;
      @media (min-width: 1000px) {
        width: 50%;
        margin-bottom: 0;
      }
      h4 {
        font-family: Raleway;
        font-style: normal;
        font-weight: bold;
        font-size: 28px;
        line-height: 109.4%;
        text-align: left;
        margin-top: 20px;
      }
      p {
        font-family: Raleway;
        font-style: normal;
        font-weight: normal;
        line-height: 26px;
        margin-left: 5%;
      }
    }
    img {
      position: absolute;
      object-fit: cover;
      width: 45%;
      max-height: 400px;
      right: 0;
      bottom: -15%;
    }
  }
  @media (min-width: 600px) {

  }
}

  .quote {
    position: relative;
    display: inline-block;
    width: auto;
    margin-top: 100px;
    max-width: 80%;
    margin-bottom: 0;
    @media (min-width: 1000px) {
      margin-bottom: 20vh;
    }
    p {
      font-family: Raleway;
      font-style: normal;
      font-weight: 900;
      text-align: left;
      //font-size: 38px;
      font-size: calc(22px + (38 - 22) * ((100vw - 300px) / (1600 - 300)));
      line-height: 94.9%;
      letter-spacing: -0.03em;
      color: white;
      max-width: 500px;
      opacity: 0.5;
    }
    #t1 {
      top: 0;
      left: 0;
    }
    #t2 {
      bottom: 0;
      right: 0;
    }
    .thick {
      position: absolute;
      font-family: Raleway;
      font-style: normal;
      font-weight: bold;
      font-size: 250px;
      color: white;
      opacity: 0.2;
      line-height: 0;
    }
  }

</style>
