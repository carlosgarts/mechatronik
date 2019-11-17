<template>
  <div class="solution-footer">
    <h3>Si necesitas mas <br> mira nuestros <nuxt-link to="/servicios">Servicios</nuxt-link> </h3>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
  .solution-footer {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 5;
    font-size: 18px;
    height: 150px;
    width: 100%;
    background: rgb(255,255,255);
    background: linear-gradient(0deg, rgba(255,255,255,1) 0%, rgba(255,255,255,1) 60%, rgba(255,255,255,0) 100%);
    @media (min-width: 1000px) {
      font-size: 25px;
      height: 300px;
    }
    a {
      color: #65A3AE;
    }
  }
</style>
