<template>
  <div class="section">
    <div class="title--bar">
      <div class="tbb">
        <h2><strong>SERVICIOS</strong></h2>
      </div>
      <p>La tecnología de punta y la competencia en el campo de la ingeniería mecánica y el desarrollo de software permiten un proceso de servicio completo
        teniendo en cuenta los requisitos específicos del cliente, a través de la planificación de sistemas completos e integraciones de sistema,
        en Mechatronik-Lösungen los apoyamos desde el prototipo hasta la producción en masa.</p>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
.section {
  min-height: 400px;
}

.title--bar {
  display: block;
  width: 100%;
  background: url('../../assets/images/soluciones-servicios/sol1.jpg') no-repeat;
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
