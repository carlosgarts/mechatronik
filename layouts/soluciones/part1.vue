<template>
  <div class="section">
    <div id="soluciones--1">
      <div class="title--bar">
        <div class="tbb">
          <h2><strong>SERVICIOS & SOLUCIONES</strong></h2>
        </div>
      </div>
      <div class="beneficios">
        <h4 v-scroll-reveal.reset>Beneficios y próximos pasos en <br> Comisionamiento Virtual</h4>
      </div>
      <img class="beneficios--linea"src="@/assets/svg/proceso1.svg" v-scroll-reveal.reset alt="wrokline">

      <div class="aplicaciones">
        <div class="frames">
            <div class="frame" id="frame1">
              <div class="content" v-scroll-reveal.reset>
                <h5>Algunas <br> aplicaciones</h5>
                <ul>
                  <li>
                    <strong>Speed Positioning</strong> <br>
                    Gantry, index tables, actuators
                  </li>
                  <li>
                    <strong>Continuous operation</strong> <br>
                    Bombs, fans, conveyours
                  </li>
                  <li>
                    <strong>Synchronous operation</strong> <br>
                    FlyingSaw, Gearing, Camming, Path
                  </li>
                  <li>
                    <strong>Product Handling Robots</strong> <br>
                    2GDL mechanisms or more, traceability
                  </li>
                  <li>
                    <strong>Control numérico</strong> <br>
                    CNC Machine
                  </li>
                </ul>
              </div>
              <div class="side-tag"> <span>&#9472&#9472&#9472</span> Soluciones</div>
            </div>
        </div>
      </div>

      <div class="resources">
        <div class="comision">
          <h4 >De la simulación al <br> comisionamiento virtual</h4>
          <img src="@/assets/svg/proceso2.svg" alt="wrokline">
        </div>

        <div class="multi--image">
          <img class="desktop-show" src="@/assets/images/multi.png" alt="engineer">
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
  overflow: hidden;
}

#soluciones--1 {
  .title--bar {
    display: block;
    background: url('../../assets/images/Soluciones/fondo-1.jpg') no-repeat;
    background-size: cover;
    margin-top: 0;
    height: 400px;
    display: flex;
    align-items: center;
    margin-bottom: 110px;
    .tbb {
      h2 {
        font-size: calc(24px + (70 - 24) * ((100vw - 300px) / (1600 - 300)));
        font-family: Raleway;
        font-style: normal;
        font-weight: 400;
      }
    }
  }
}

.beneficios {
  position: absolute;
  top: 400px;
  z-index: 15;
  background-color: white;
  width: 80%;
  margin-left: 10%;
  margin-right: 10%;
  -webkit-box-shadow: 0px 7px 18px 4px rgba(0,0,0,0.42);
  -moz-box-shadow: 0px 7px 18px 4px rgba(0,0,0,0.42);
  box-shadow: 0px 7px 18px 4px rgba(0,0,0,0.42);
  height: 250px;
  @media (min-width: 350px) {
    height: 300px;
  }
  h4 {
    font-size: calc(20px + (38 - 20) * ((100vw - 300px) / (1600 - 300)));
  }
}
.beneficios--linea {
  z-index: 16;
  position: absolute;
  width: 100%;
  top: 530px;
  left: 0;
}

.aplicaciones {
  height: 100vh;
  width: 100%;
  background: url('../../assets/images/Soluciones/fondo-2.jpg') no-repeat;
  background-size: cover;
  background-attachment: fixed;
  color: white;
  display: flex;
  align-items: flex-end;
  .frames {
    margin-left: 10%;
    .side-tag {
      left: -10%;
      @media (min-width: 1000px) {
        left: -25%;
      }
    }
    .frame {
    }
  }
}

.resources {
  height: auto;
  width: 100%;
  background: url('../../assets/images/Soluciones/fondo-3.jpg') no-repeat;
  background-size: cover;
}

.comision {
  display: flex;
  flex-flow: column;
  h4 {
    position: relative;
    text-align: center;
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    font-size: calc(18px + (38 - 18) * ((100vw - 300px) / (1600 - 300)));
    line-height: 1.1;
    color: #000;
    z-index: 2;
    margin-bottom: 60px;
    margin-top: 60px;
  }
  img {
    width: 99vw;
  }
}

.frames {
  .frame {
    position: relative;
    margin-top: 50px;
    margin-bottom: 100px;
    margin-left: 5%;
    margin-right: 5%;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-content: stretch;
    @media (min-width: 1000px) {
      flex-direction: row;
      justify-content: space-between;
    }
  }
  .content {
    align-self: center;
    width: 100%;
    @media (min-width: 1000px) {
    }
  }
  h5 {
    position: relative;
    text-align: left;
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    font-size: calc(18px + (28 - 18) * ((100vw - 300px) / (1600 - 300)));
    line-height: 1.1;
    color: white;
    z-index: 3;
    margin: 0;
  }
  ul {
    position: relative;
    text-align: left;
    list-style: none;
    padding: 0;
    z-index: 3;
  }
  li {
    margin-bottom: 5px;
  }
  img {
    width: 490px;
    height: 490px;
    object-fit: cover;
    position: relative;
    z-index: 3;
  }
  .adapt-img {
      width: 100%;
      height: auto;
    @media (min-width: 530px) {
      height: 90vh;
    }
    @media (min-width: 1000px) {
      width: 490px;
      height: 490px;
    }
  }
  .side-tag {
    left: -5%;
    color: white;
    span {
      color: white;
      margin-right: 15px;
    }
  }
}

#cont2 {
  display: block;
  float: left;
  clear: left;
  margin-top: 50px;
  margin-left: 5%;
  @media (min-width: 1000px) {
    margin-top: 0;
  }
}

.multi--image {
  position: static;
  margin-top: 50px;
  padding-bottom: 100px;
  z-index: 25;
  img {
    width: 80%;
    @media (min-width: 1000px) {
      width: 60%;
    }
  }
}

.adapt-img {
  width: 100%;
  height: 30vh;
  @media (min-width: 1150px) {
    width: 490px;
    height: 490px;
  }
}

.wide-img {
  display: block;
  width: 100%;
  max-height: 50vh;
  margin-top: 150px;
  @media (min-width: 1150px) {
    display: none;
  }
}
.frame-img {
  display: none;
  @media (min-width: 1150px) {
    display: block;
  }
}

.desktop-show {
    display: inline;
    margin-bottom: 10vh;
}

////////////////////////seccion 2

#soluciones--2 {
  margin-left: 10%;
  margin-right: 10%;
  width: 80%;
  @media (min-width: 1000px) {
    width: 90%;
    margin-right: 0;
  }
}
.fabricacion {
  position: relative;
  background-color: white;
  margin-left: 5%;
  margin-right: 5%;
  .frame {
    position: relative;
    margin-top: 50px;
    margin-bottom: 100px;
    display: flex;
    justify-content: flex-start;
    flex-flow: column-reverse;
    @media (min-width: 1000px) {
      justify-content: space-between;
      flex-flow: row nowrap;
    }
  }
  .content {
    align-self: flex-start;
    text-align: left;
    @media (min-width: 1000px) {
      align-self: center;
      text-align: left;
    }
  }
  .title {
    position: relative;
    display: inline-block;
    left: 0;
    @media (min-width: 1000px) {
      left: -50px;
    }
    h5 {
      position: relative;
      text-align: left;
      font-family: Raleway;
      font-style: normal;
      font-weight: bold;
      font-size: calc(20px + (70 - 20) * ((100vw - 300px) / (1600 - 300)));
      line-height: 1.1;
      color: #65A3AE;
      font-weight: 900;
      z-index: 3;
      margin: 0;
    }
    .ampersand {
      transition: 0.5s;
      position: absolute;
      font-family: Raleway;
      color: rgba(101, 163, 174, 0.25);
      right: 0;
      //font-size: 250px;
      font-size: calc(50px + (150 - 50) * ((100vw - 300px) / (1600 - 300)));
      font-weight: 900;

      @media (min-width: 600px) {
      }
      @media (min-width: 800px) {
      }
    }
  }
  p {
    position: relative;
    text-align: left;
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    font-size: calc(16px + (24 - 16) * ((100vw - 300px) / (1600 - 300)));
    line-height: 1.1;
    max-width: 400px;
    color: #65A3AE;
    z-index: 3;
    margin: 0;
  }
  ul {
    position: relative;
    text-align: left;
    list-style: none;
    padding: 0;
    z-index: 3;
  }
  li {
    margin-bottom: 5px;
  }
  img {
    width: 600px;
    height: 600px;
    object-fit: cover;
    position: relative;
    z-index: 3;
  }
  .adapt-img {
      width: 100%;
      height: auto;
    @media (min-width: 530px) {
      height: 90vh;
    }
    @media (min-width: 1000px) {
      width: 450px;
      height: 450px;
    }
    @media (min-width: 1100px) {
      width: 600px;
      height: 600px;
    }
  }
  .side-tag {
    left: -5%;
  }
}
</style>
