<template>
  <div class="section">
    <div id="soluciones--4">
      <img class="adapt-img" src="@/assets/images/Soluciones/diseño-y-fabricacion.jpg" alt="ingenieria">
      <div class="frames">
        <div class="frame">
          <div id="cont2" class="content">
            <div class="tbb">
              <h2>Experiencia <strong>Industrial</strong> </h2>
            </div>
          <ul>
            <li>
              Proyectos especiales llave en mano orientados a la industria 4.0.
            </li>
            <li>
              Servosistemas
            </li>
            <li>
              Robótica industrial para aplicaciones de ensamble e inspección.
            </li>
            <li>
              Trazabilidad de líneas de producción.
            </li>
            <li>
              Líneas de inspección.
            </li>
          </ul>
          </div>
        </div>
      </div>

      <div id="soluciones--2">
        <div class="fabricacion">
          <div class="frame">
            <div class="content">
              <div class="title">
                <h5>DISEÑO Y FABRICACIÓN </h5>
              </div>
              <p>La fabricación de un producto que se adapte a sus necesidades</p>
              <ul>
                <li>
                  <strong>1 Vertical machining center CNC:</strong> <br>
                  Hass TM-1 Milling Machine ( 12” x 33 “ )
                </li>
                <li>
                  <strong>2 Vertical machining center CNC :</strong> <br>
                  SMTCL VMC-850-E ( 16” X 39 “ )
                </li>
                <li>
                  <strong>1 Vertical machining center CNC:</strong> <br>
                  Bridgeport Interact 4 ( 14” x 36” )
                </li>
                <li>
                  <strong>1 Horizontal machining center:</strong> <br>
                  Hass Turning center SL-20 10.3 “ dia. X 20 “ long.
                </li>
                <li>
                  <strong>4 Vertical Milling machines:</strong> <br>
                  2” x 39”
                </li>
                <li>
                  <strong>1 Waterjet machine CNC:</strong> <br>
                  1 Waterjet machine CNC with cap. to cut pcs of 2” x 72” x 120“
                </li>
              </ul>
            </div>
          </div>
          <div class="side-tag"> <span>&#9472&#9472&#9472</span> Soluciones</div>
        </div>
      </div>
      <div class="quote">
        <div id="t1" class="thick">“</div>
        <p>Desarrollamos proyectos llave en mano enfocados en la automatización de sus procesos de manufactura.</p>
        <div id="t2" class="thick">”</div>
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
  background: url('../../assets/images/Soluciones/fondo-4.jpg') no-repeat;
  background-size: cover;
  background-attachment: fixed;
}

.tbb {
  margin-left: 0;
  h2 {
    font-size: calc(24px + (60 - 24) * ((100vw - 300px) / (1600 - 300)));
    font-family: Raleway;
    font-style: normal;
    font-weight: 400;
  }
}

#soluciones--4 {
  position: relative;
  width: 100%;
  .adapt-img {
      display: none;
    @media (min-width: 530px) {
      display: block;
      position: absolute;
      top: 100px;
      right: 0;
      width: 300px;
      height: 300px;
      object-fit: cover;
    }
    @media (min-width: 1000px) {
      width: 490px;
      height: 490px;
    }
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
    }
  }
  .content {
    align-self: center;
    width: 100%;
    display: flex;
    flex-flow: column;
    align-items: flex-start;
    color: white;
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
    margin-left: 5%;
    position: relative;
    text-align: left;
    list-style: none;
    padding: 0;
    z-index: 3;
  }
  li {
    margin-bottom: 15px;
    width: 80%;
  }
  img {
    width: 490px;
    height: 490px;
    object-fit: cover;
    position: relative;
    z-index: 3;
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
  color: white;
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
    @media (min-width: 1000px) {
      left: -50px;
    }
    h5 {
      position: relative;
      text-align: left;
      font-family: Raleway;
      font-style: normal;
      font-weight: bold;
      font-size: calc(20px + (50 - 20) * ((100vw - 300px) / (1600 - 300)));
      line-height: 1.1;
      color: white;
      font-weight: 900;
      z-index: 3;
      margin: 0;
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
    margin-left: 7%;
  }
  li {
    margin-bottom: 15px;
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
    color: white;
    span {
      color: white;
    }
  }
}

//Quote

.quote {
  position: relative;
  display: block;
  float: right;
  width: auto;
  margin-top: 100px;
  max-width: 80%;
  margin-bottom: 0;
  margin-right: 10%;
  margin-left: 20%;
  margin-bottom: 10vh;
  @media (min-width: 1000px) {
    margin-bottom: 20vh;
  }
  p {
    font-family: Raleway;
    font-style: normal;
    font-weight: 900;
    text-align: left;
    font-size: calc(22px + (38 - 22) * ((100vw - 300px) / (1600 - 300)));
    line-height: 94.9%;
    letter-spacing: -0.03em;
    color: white;
    max-width: 500px;
    opacity: 0.8;
  }
  #t1 {
    top: 100px;
    left: -100px;
  }
  #t2 {
    bottom: -20px;
    right: -50px;
  }
  .thick {
    position: absolute;
    display: block;
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    font-size: 250px;
    color: white;
    opacity: 0.5;
    line-height: 0;
  }
}

</style>
