<template>
  <div class="section">
    <div id="mision--vision">
      <img class="parallax-background" v-rellax="{speed: -10, vertical: true, horizontal: false}" src="../../assets/images/Soluciones/bg-clear.png" alt="">
      <div class="content" v-scroll-reveal.reset>
        <div class="info">
          <div class="mision">
            <h1>Misión </h1>
            <p>Proveer a nuestros clientes la mejor solución garantizando la mejor inversión en el incremento de su productividad.</p>
          </div>
        </div>
        <div class="info">
          <div class="vision">
            <h1>Visión</h1>
            <p>Mechatronik Group se compromete a ser el socio más confiable en tecnología, innovación y desarrollo, trabajando con calidad y buen servicio.</p>
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
  // background-image: url('../../assets/images/Compañia/fondo-2.jpg');
  background-color: white;
}
#mision--vision {
  width: 100%;
  position: relative;
  @media (min-width: 600px) {
  }
  .parallax-background {
    width: 100%;
    position: absolute;
    z-index: 1;
  }
  .content {
    width: 100%;
    height: auto;
    display: grid;
    grid-template-columns: 100%;
    @media (min-width: 600px) {
      height: 50vh;
      grid-template-columns: 50% 50%
    }
    h1 {
      font-family: Raleway;
      font-style: normal;
      font-weight: bold;
      font-size: calc(30px + (70 - 30) * ((100vw - 300px) / (1600 - 300)));
      color: black;
      margin-top: 10px;
    }
    p {
      font-family: Raleway;
      font-style: normal;
      font-weight: normal;
      font-size: calc(16px + (22 - 16) * ((100vw - 300px) / (1600 - 300)));
      line-height: 1.4;
      text-align: center;
      color: black;
      width: 70%;
    }
    .info {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: auto;
    }
    .vision {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: auto;
      margin-bottom: 10vh;
      @media (min-width: 1000px) {
        border-left: 2px solid black;
        margin-bottom: 0;
      }
      h1 {
        border-top: 2px solid white;
        padding-top: 10vh;
        @media (min-width: 1000px) {
          border-top: none;
          padding-top: 0;
        }
      }
    }
    .mision {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: auto;
      margin-bottom: 10vh;
      margin-top: 10vh;
      @media (min-width: 1000px) {
        margin-bottom: 0;
        margin-top: 0;
      }
    }
  }
}

</style>
