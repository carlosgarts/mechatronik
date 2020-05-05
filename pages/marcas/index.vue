<template>
  <div class="container">
    <marcasheader/>
    <marcas/>
    <marcasfooter/>
  </div>
</template>

<script>
import marcasheader from '~/layouts/marcas/marcas-header.vue'
import marcas from '~/layouts/marcas/marcas.vue'
import marcasfooter from '~/layouts/marcas/marcas-footer.vue'

export default {
  components: {
    marcasheader,
    marcas,
    marcasfooter
  }
}
</script>

<style lang="scss">
  .container {
    background-color: white;
  }

  .preludio {
    width: 90%;
    @media (min-width: 1000px) {
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
      max-width: 100%;
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
