<template>
  <div class="section">
    <div class="title--bar">
      <div class="gradiente"></div>
      <div class="title">
        <h2><strong>SERVICIOS</strong></h2>
      </div>
    </div>
    <div class="sub-title">
      <div class="pre">
        <h4>Featured services</h4>
        <h3 class="item-title">
          <img class="dot-shape" src="@/assets/svg/mechatronik-adorno.svg" alt="">
          Nuestras areas de experiencia.
        </h3>
      </div>
      <div class="excerpt">
        <p>La tecnología de punta y la competencia en el campo de la ingeniería mecánica y el desarrollo de software permiten un proceso de servicio completo
          teniendo en cuenta los requisitos específicos del cliente, a través de la planificación de sistemas completos e integraciones de sistema,
          en Mechatronik-Lösungen los apoyamos desde el prototipo hasta la producción en masa.</p>
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
  min-height: 300px;
  display: block;
}

.title--bar {
  display: block;
  position: relative;
  width: 100%;
  background: url('../../assets/images/soluciones-servicios/sol1.jpg') no-repeat;
  //background: -webkit-linear-gradient(to right, rgba(#64b3f4, 80%), rgba(#c2e59c, 10%));  /* Chrome 10-25, Safari 5.1-6 */
  //background: linear-gradient(to right, rgba(#64b3f4, 80%), rgba(#c2e59c, 10%)); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  background-size: cover;
  background-attachment: fixed;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-flow: column;
  @media (min-width: 1000px) {
    height: 40vh;
  }
  .gradiente {
    display: block;
    position: absolute;
    z-index: 0;
    width: 100%;
    height: 100%;
    //background: -webkit-linear-gradient(to right, rgba(#64b3f4, 80%), rgba(#c2e59c, 10%));  /* Chrome 10-25, Safari 5.1-6 */
    //background: linear-gradient(to right, rgba(#64b3f4, 80%), rgba(#c2e59c, 10%)); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    background: linear-gradient(90deg, rgba(101,163,174,1) 0%, rgba(100,179,244,0.3338469176733193) 100%);
    //opacity: 0.5;
  }
  p {
    color: white;
    line-height: 1.5;
    margin-left: 10%;
    margin-right: 10%;
    text-align: left;
    margin-bottom: 50px;
    z-index: 5;
    @media (min-width: 1000px) {
      margin-left: 5%;
      margin-right: 5%;
    }
  }
  .title {
    color: white;
    margin-top: 10%;
    margin-bottom: 10%;
    margin-left: 10%;
    margin-right: 10%;
    z-index: 5;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
   //  background: -webkit-linear-gradient(#eee, #333);
   // -webkit-background-clip: text;
   // -webkit-text-fill-color: transparent;
    @media (min-width: 1000px) {
      margin-top: 0;
      margin-bottom: 0;
      margin-left: 5%;
      margin-right: 5%;
    }
    h2 {
      font-size: calc(32px + (70 - 32) * ((100vw - 300px) / (1600 - 300)));
      font-style: normal;
      font-weight: 400;
      margin-bottom: 20px;
      // &:after {
      //   content: '';
      //   display: block;
      //   margin-top: 20px;
      //   background-color: white;
      //   height: 1px;
      //   width: 50%;
      // }
    }
  }
}

.sub-title {
  width: 80%;
  margin-left: 10%;
  margin-right: 10%;
  margin-top: 25px;
  margin-bottom: 25px;
  text-align: left;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  flex-direction: column;
  @media (min-width: 1000px) {
    flex-direction: row;
  }
  .pre {
    width: 100%;
    @media (min-width: 1000px) {
      width: 50%;
      border-right: 1px gray solid;
    }
    h4 {
      color: #65A3AE;
      margin-top: 7px;
      margin-bottom: 7px;
      padding-left: 50px;
      @media (min-width: 480px) {
        padding-left: 70px;
      }
    }
    h3{
      transition: 0.5s;
      position: relative;
      font-size: 28px;
      text-align: left;
      padding-left: 50px;
      color: black;
      word-break: normal;
      @media (min-width: 480px) {
        font-size: 45px;
        padding-left: 70px;
      }
    }
    .dot-shape {
      position: absolute;
      left: 0;
      height: 35px;
      margin-top: 10px;
      @media (min-width: 480px) {
        height: 50px;
      }
    }
  }
  .excerpt {
    width: 100%;
    @media (min-width: 1000px) {
      width: calc(50% - 25px);
      margin-left: 25px;
    }
    p {
      text-align: justify;
      line-height: 1.5;
    }
  }
}
</style>
