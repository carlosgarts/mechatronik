<template>
  <div class="short-section">
    <div id="cifras">
      <h1>¡OPTIMIZANDO EL FUNCIONAMIENTO DE SU EMPRESA!</h1>
      <!-- <h3>HECHOS & CIFRAS</h3> -->
      <div class="cards">
        <div class="card">
          <img class="icon" src="@/assets/images/SVG/Fundada.svg" alt="Fundada">
          <div class="title">Fundada</div>
          <div class="number">2018</div>
        </div>
        <div class="card">
          <img class="icon" src="@/assets/images/SVG/Inversion.svg" alt="I+D">
          <div class="title">Inversión en I+D</div>
          <div class="number">10%</div>
        </div>
        <div class="card">
          <img class="icon" src="@/assets/images/SVG/Experiencia Industrial.svg" alt="Experiencia Industrial">
          <div class="title">Experiencia Industrial</div>
          <div class="number">+25</div>
        </div>
        <div class="card">
          <img class="icon" src="@/assets/images/SVG/Asociaciones.svg" alt="Asociaciones">
          <div class="title">Asociaciones & <br> Socios - Comerciales</div>
          <div class="number">12</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data: function () {
    return {

    }
  },
  methods: {

    }
}
</script>

<style lang="scss" scoped>
#cifras{
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  text-align: center;
  h1 {
    color: #000;
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    margin-bottom: 0;
    font-size: 30px;
    margin-top: 0;
  }
  h3{
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    color: #000;
    margin-top: 25px;
    border: 2px black solid;
    padding: 10px;
  }
}

.cards {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  width: 100%;
  .card{
    margin: 30px;
    width: 200px;
    .icon {
      width: 80px;
      margin: 20px;
    }
    .title {
      font-family: Raleway;
      font-style: normal;
      font-weight: normal;
      font-size: 16px;
      line-height: 26px;
      color: #000000;
    }
    .number {
      font-family: Raleway;
      font-style: normal;
      font-weight: 900;
      font-size: 16px;
      line-height: 26px;
      color: #000;
    }
  }
}
</style>
