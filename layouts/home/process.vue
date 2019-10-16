<template>
  <div class="section">
    <div id="process">
      <h3>Algunas <strong>aplicaciones</strong></h3>
      <div class="cards">
        <div id="card-1" class="card">
          <div class="tbb">
          <h2>Synchronous <br> Operation</h2>
          </div>
          <p class="text">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
            <br> <br>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
          </p>
        </div>
        <div id="card-2" class="card">
          <div class="tbb">
          <h2>Continuous <br> operation</h2>
          </div>
          <p class="text">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
          <br> <br>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
        </div>
        <div id="card-3" class="card">
          <div class="tbb">
          <h2>Synchronous <br> Operation</h2>
          </div>
          <p class="text">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
            <br> <br>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
          </p>
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
    background: #65A3AE;
    background-image: url('../../assets/images/Inicio/fondo-inicio.jpg');
    background-attachment: fixed;
    z-index: -10;
    align-items: flex-start;
  }
  #process {
    display: block;
    width: 100%;
    @media (min-width: 910px) {
      height: 100vh;
    }
    @media (min-width: 1000px) {
      height: 700px;
    }
    h3 {
      color: white;
      text-align: left;
      font-family: Raleway;
      font-style: normal;
      font-weight: normal;
      font-size: calc(35px + (55 - 35) * ((100vw - 300px) / (1600 - 300)));
      margin: 60px;
    }
    img {
      width: 100%;
    }
  }

  .cards {
    display: flex;
    color: white;
    width: 90%;
    justify-content: center;
    flex-wrap: wrap;
    margin-left: 5%;
    margin-right: 5%;
    margin-bottom: 100px;
    @media (min-width: 900px) {
      justify-content: center;
      margin-bottom: 0;
    }
    @media (min-width: 1200px) {
      justify-content: space-between;
    }
    .card {
      transition: 0.5s;
      padding: 10px;
      padding-left: 20px;
      @media (min-width: 900px) {
        min-width: 210px;
        width: 200px;
        height: 200px;
        margin-left: 20px;
        margin-right: 20px;
        padding: 10px;
      }
      @media (min-width: 1200px) {
        width: 280px;
        height: 400px;
      }
      .tbb {
        margin: 0;
        h2 {
          padding-bottom: 15px;
          font-size: 28px;
        }
      }
      &:hover .text{
        opacity: 1;
      }
      .text {
        transition: 0.5s ease-in;
        opacity: 1;
        overflow: hidden;
        text-align: justify;
        @media (min-width: 910px) {
          opacity: 0;
        }
      }
      h2 {
        text-align: left;
      }
    }
  }
</style>
