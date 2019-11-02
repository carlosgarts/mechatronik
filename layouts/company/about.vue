<template>
  <div class="section">
    <div id="about">
      <div class="text animated fadeIn">
        <div class="tbb">
        <h2>Acerca <strong>de Mechatronik</strong></h2>
        </div>
        <p>
          Somos una compañía mexicana dedicada al diseño e integración de soluciones para la industria. Ofrecemos un enfoque de innovación, calidad y rentabilidad a largo plazo, combinado con un excelente servicio al cliente, productos superiores y una vasta experiencia que le dará el mejor valor posible en la industria.
        </p>
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
  background: url('../../assets/images/Compañia/fondo-1.jpg') no-repeat;
  background-size: cover;
  background-attachment: fixed;
}
#about {
  margin-top: 100px;
  height: auto;
  width: 100vw;
  align-self: flex-end;
  @media (min-width: 1000px) {
    margin-top: 0;
    height: calc(100vh - 100px);
    width: 100vw;
    }
  }

  .tbb {
    margin: 0;
  }

  .text {
    height: 100%;
    width: 100%;
    text-align: left;
    display: flex;
    flex-flow: column;
    justify-content: flex-end;
    align-items: flex-start;
    padding-bottom: 3%;
    color: white;
    margin-left: 5%;
    p {
      width: 90%;
      line-height: 1.3;
      @media (min-width: 1000px) {
        width: 60%;
      }
    }
  }

</style>
