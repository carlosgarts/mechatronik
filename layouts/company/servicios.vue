<template>
  <div class="section">
    <div id="company--services">
      <div class="fabricacion">
        <div class="frame">
          <div class="content">
            <div class="tbb">
              <h2>Experiencia <strong>Industrial</strong></h2>
            </div>
            <ul>
              <li>
                Diseño Mecánico
              </li>
              <li>
                Diseño Eléctrico
              </li>
              <li>
                Manufactura Aditiva
              </li>
              <li>
                Ingeniería de Control
              </li>
            </ul>
            <div class="tbb">
              <h2>Otros <strong>Servicios</strong></h2>
            </div>
            <ul>
              <li>
                Outsourcing de personal
              </li>
              <li>
                Consultoría en Industria 4.0
              </li>
              <li>
                Consultoría en motion control
              </li>
            </ul>
          </div>
        </div>
        <div class="side-tag"> <span>&#9472&#9472&#9472</span> Servicios</div>
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
  background-color: white;
  flex-direction: column;
  height: calc(100vh - 110px);
  //min-height: calc(100vh - 110px);
  margin-top: 110px;
  background: url('../../assets/images/Soluciones/fondo-servicios.jpg') no-repeat;
  background-size: cover;
  @media (min-width: 1000px) {
    height: calc(100vh - 135px);
    min-height: calc(100vh - 135px);
    margin-top: 135px;
  }
}
#company--services {
  margin-left: 10%;
  width: 90%;
}
.fabricacion {
  position: relative;
  margin-left: 5%;
  margin-right: 5%;
  .frame {
    position: relative;
    display: flex;
    justify-content: space-between;
  }
  .content {
    align-self: center;
    text-align: left;
    display: flex;
    align-items: flex-start;
    flex-flow: column;
    width: 90%;
    .tbb {
      margin-left: 0;
    }
  }
  h4 {
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
    margin-bottom: 50px;
    color: white;
  }
  li {
    margin-bottom: 10px;
  }
  .side-tag {
    left: -5%;
    color: white;
    span {
      color: white;
    }
  }
}
</style>
