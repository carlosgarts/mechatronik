<template>
  <div class="section">
    <div class="title--bar">
      <div class="tbb">
        <h2><strong>SOLUCIONES</strong></h2>
      </div>
      <p>Nuestras soluciones están basadas en nuestra experiencia durante el
        ciclo de desarrollo, desde la definición de requisitos hasta la
        integración de sistemas y validación de sistemas mecatrónicos con una
        densidad de potencia optima y alta confiabilidad, nuestros ingenieros
        tienen experiencia en el desarrollo de un sistema altamente dinámico en control de movimiento.</p>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
.section {
  min-height: 300px;
}

.title--bar {
  display: block;
  width: 100%;
  background: url('../../assets/images/soluciones-servicios/serv1.jpg') no-repeat;
  background-size: cover;
  background-attachment: fixed;
  height: auto;
  display: flex;
  flex-flow: column;
  align-items: flex-start;
  justify-content: center;
  @media (min-width: 1000px) {
    height: 50vh;
  }
  p {
    color: white;
    line-height: 1.5;
    margin-left: 10%;
    margin-right: 10%;
    text-align: left;
    margin-bottom: 50px;
    @media (min-width: 1000px) {
      margin-left: 5%;
      margin-right: 5%;
    }
  }
  .tbb {
    margin-top: 10%;
    margin-left: 10%;
    margin-right: 10%;
    @media (min-width: 1000px) {
      margin-top: 0;
      margin-left: 5%;
      margin-right: 5%;
    }
    h2 {
      font-size: calc(32px + (70 - 32) * ((100vw - 300px) / (1600 - 300)));
      font-family: Raleway;
      font-style: normal;
      font-weight: 400;
    }
  }
}
</style>
