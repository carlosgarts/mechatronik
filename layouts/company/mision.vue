<template>
  <div class="section">
    <div id="mision--vision">
      <!-- <img class="parallax-background" v-rellax="{speed: -10, vertical: true, horizontal: false}" src="../../assets/images/Soluciones/bg-clear.png" alt=""> -->
      <div class="content" v-scroll-reveal.reset>
        <contenido/>
      </div>
    </div>
  </div>
</template>

<script>
import contenido from './content'
export default {
  components: {
    contenido
  }
}
</script>

<style lang="scss" scoped>
.section {
  // background-image: url('../../assets/images/Compañia/fondo-2.jpg');
  width: 90%;
  background-color: white;
  align-items: flex-start;
  @media (min-width: 800px) {
    width: 80%;
  }
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

}

</style>
