<template>
  <div class="solution-footer">
    <div class="text">
      <img src="@/assets/svg/tornillo.svg" alt="servicios">
      <div>
        <h4 class="p1">Mire nuestros servicios</h4>
        <p class="p2">Con Mechatronik cuenta con el soporte que su empresa necesite</p>
      </div>
    </div>
    <nuxt-link to="/servicios">Ver mas</nuxt-link>
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
    justify-content: space-between;
    flex-flow: column;
    z-index: 5;
    font-size: 18px;
    height: auto;
    min-height: 150px;
    width: 100%;
    padding: 5%;
    background-color: #65A3AE;
    margin-top: 50px;
    margin-bottom: 50px;
    @media (min-width: 700px) {
      flex-flow: row;
    }
    @media (min-width: 1000px) {
      font-size: 25px;
      padding: 0 8%;
      height: 150px;
    }
    h4, p {
      color: white;
    }
    .p1 {
      font-size: 27px;
      margin-top: 5px;
      margin-bottom: 5px;
      text-align: center;
      @media (min-width: 700px) {
        text-align: left;
      }
    }
    .p2 {
      font-size: 18px;
      margin-top: 5px;
      margin-bottom: 5px;
      text-align: center;
      @media (min-width: 700px) {
        text-align: left;
      }
    }
    a {
      transition: 0.5s;
      color: white;
      text-decoration: none;
      border: 4px solid white;
      padding: 9px 14px;
      margin-bottom: 16px;
      font-weight: bold;
      margin: 15px 0;
      &:hover {
        background-color: white;
        color: #65A3AE;
      }
    }
    img {
      max-height: 100px;
      margin-right: 15px;
    }
    .text {
      display: flex;
      width: auto;
      align-items: center;
      flex-direction: column;
      @media (min-width: 700px) {
        flex-direction: row;
        justify-content: center;

      }
    }
  }
</style>
