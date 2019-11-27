<template>
  <div class="section">
    <div id="productos--intro">
      <div class="intro">
        <div class="frame">
          <div class="content">
            <div class="title">
              <img class="prod-logo" src="https://pngimage.net/wp-content/uploads/2018/05/brand-png-9.png" alt="neugart">
              <h4>Brands <br>Overview</h4>
            </div>
            <img class="movile-images" src="https://i2.wp.com/bmmetalroofing.com/wp-content/uploads/2016/01/test.jpg?w=800" alt="manual">
            <p>
              Neugart es una empresa familiar entre los fabricantes de cajas de cambios, fundado en 1928. Neugart desarrolla, y produce engranajes planetarios y reductores personalizadas.
              <br><br>
              Neugart ha estado apoyando a todos los sectores industriales durante más de medio siglo.
              <br><br>
              La experiencia mecánica e industrial incluye todo, desde la automatización y la robótica hasta la alimentación y el envasado, pasando por la medicina y la farmacia.
            </p>
          </div>
        </div>
        <div class="side-tag"> <span>&#9472&#9472&#9472</span> Products</div>
      </div>
    </div>
    <div class="movile-images">
      <img src="@/assets/images/product-section/catalog.jpg" alt="manual">
      <img class="gadget2" src="../../assets/images/rectangle.jpg" alt="pieces">
    </div>
    <div class="detail">
      <div class="text">
        <p>Confiamos en el software de cálculo para el diseño de unidades complejas,
        estas herramientas nos ayudan a dimensionar la aplicación para el análisis,
        la optimización, la selección y la validación de su sistema de control.</p>
      </div>
      <img class="desktop-image" src="@/assets/images/product-section/catalog.jpg" alt="manual">
    </div>
    <div class="gadget desktop-image">
      <img src="../../assets/images/rectangle.jpg" alt="pieces">
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
  //flex-direction: column;
  display: block;
  margin-top: 100px;
  @media (min-width: 1000px) {
    padding-bottom: 25vh;
  }
}
#productos--intro {
  width: 100%;
  height: auto;
  background-image: none;
  @media (min-width: 1000px) {
    height: 110vh;
    background: url('../../assets/images/test-background.jpg') no-repeat;
    background-size: cover;
  }
}

.intro {
  position: relative;
  width: 100%;
  height: auto;
  margin-left: 10%;
  display: block;
  align-items: center;
  @media (min-width: 1000px) {
    display: flex;
    margin-top: 0;
    height: 100vh;
    margin-left: 10%;
  }
  .frame {
    position: relative;
    margin-top: 50px;
    margin-bottom: 100px;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    max-width: 80%;
    @media (min-width: 1000px) {
      height: 110vh;
      max-width: 50%;
    }
  }
  .content {
    align-self: center;
    text-align: left;
  }
  .title {
    position: relative;
    display: inline-block;
    margin-top: 10vh;
    margin-bottom: 10vh;
    h4 {
      display: inline-block;
      position: relative;
      text-align: left;
      font-style: normal;
      font-weight: bold;
      font-size: calc(32px + (70 - 32) * ((100vw - 300px) / (1600 - 300)));
      line-height: 1.1;
      //color: rgba(255, 255, 255, 0.1);
      color: white;
      font-weight: 900;
      z-index: 3;
      margin: 0;
      text-shadow: -1px 0 #65A3AE, 0 1px #65A3AE, 1px 0 #65A3AE, 0 -1px #65A3AE;
    }
    .prod-logo {
      display: inline-block;
      width: 20%;
      @media (min-width: 1000px) {
        width: 100px;
      }
    }
  }
  .side-tag {
    left: -5%;
  }
}

.detail {
  position: relative;
  //background-color: #65A3AE;
  //width: 50%;
  width: 100%;
  text-align: left;
  .text {
    position: relative;
    display: inline-block;
    text-align: left;
    width: 100%;
    background-color: #65A3AE;
    padding: 20px;
    padding-left: 10%;
    font-style: normal;
    font-weight: normal;
    line-height: 23px;
    color: #FFFFFF;
    z-index: 5;
    @media (min-width: 1000px) {
      width: 40%;
      margin-top: 200px;
    }
    p {
      width: 80%;
      @media (min-width: 1000px) {
        width: 100%;
      }
    }
  }
  img {
    display: inline-block;
    position: relative;
    right: 100px;
    bottom: 50px;
    //bottom: 380px;
    width: 451px;
    height: 298px;
  }
  .desktop-image {
    display: none;
    @media (min-width: 1000px) {
      display: inline-block;
    }
  }
}

.gadget {
  text-align: right;
  img {
    height: 150px;
    width: 300px;
    margin-right: 10%;
    transform: rotate(-25deg);
  }
}

.movile-images {
  display: block;
  width: 100%;
  img {
    width: 100%;
  }
  .gadget2 {
    width: 80%;
    margin: 10px;
    transform: rotate(-5deg);
  }
  @media (min-width: 1000px) {
    display: none;
  }
}
.desktop-image {
  display: none;
  @media (min-width: 1000px) {
    display: block;
  }
}
</style>
