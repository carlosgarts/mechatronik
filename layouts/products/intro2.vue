<template>
  <div class="section">
    <div id="company--services">
      <div class="producto">
        <div class="frame">
          <div class="content">
            <h3>Planetary <br> Gearbox</h3>
            <h4>with Output Shaft</h4>
            <p>
              La caja de engranajes planetarios Neugart con eje de salida son
              adecuadas para una amplia gama de soluciones de accionamiento.
              El eje de salida está disponible en varias variaciones, por ejemplo
              con eje de salida con cuña para una transmisión de potencial confiable y
              de ajuste positivo. El eje de salida liso siendo el elemento ideal
              para lograr una conexión de ajuste forzado a un acoplamiento.
              Esto le permite alcanzar la transmisión de par máximo incluso en modo inverso.
              También puede conectar el eje de salida a su sistema de accionamiento como eje dentado.
              Debido a la baja inercia del eje de salida, las cajas de engranajes
              planetarios con eje de salida son la solución ideal para muchas aplicaciones dinámicas.
            </p>
          </div>

          <div class="selection">
            <ul>
              <li v-for="item in items">
                <img class="product" src="https://www.makerlab-electronics.com/my_uploads/2017/11/DC-Brush-Spindle-Motor-RS-775-24V-8300RPM-01.jpg" alt="product">
                <div class="pre-info">
                  <h5>PLE</h5>
                  <p>Economy planetary gearbox</p>
                </div>
                <button type="button" name="button"> <img src="../../assets/images/right.png" alt="arrow"> </button>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      items: [
        { message: 'Foo' },
        { message: 'Bar' },
        { message: 'Bar' },
        { message: 'Bar' }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.section {
  background-color: white;
}
#company--services {
  margin-left: 5%;
  margin-right: 5%;
  width: 90%;
  @media (min-width: 1000px) {
    margin-left: 10%;
    margin-right: 0;
  }
}
.producto {
  position: relative;
  background-color: white;
  margin-left: 5%;
  margin-right: 5%;
  .frame {
    position: relative;
    margin-top: 50px;
    margin-bottom: 100px;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    @media (min-width: 1000px) {
      flex-direction: row;
    }
  }
  .content {
    align-self: center;
    text-align: left;
  }
  h3 {
    display: inline-block;
    position: relative;
    text-align: left;
    font-style: normal;
    font-weight: bold;
    font-size: calc(50px + (70 - 50) * ((100vw - 300px) / (1600 - 300)));
    line-height: 1.1;
    //color: rgba(255, 255, 255, 0.1);
    color: white;
    font-weight: 900;
    z-index: 3;
    margin: 0;
    text-shadow: -1px 0 #65A3AE, 0 1px #65A3AE, 1px 0 #65A3AE, 0 -1px #65A3AE;
  }
  h4 {
    position: relative;
    text-align: left;
    font-style: normal;
    font-weight: bold;
    font-size: calc(18px + (28 - 18) * ((100vw - 300px) / (1600 - 300)));
    line-height: 1.1;
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
    margin-bottom: 50px;
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
  .side-tag {
    left: -5%;
  }
}

.selection {
  margin: 0;
  @media (min-width: 1000px) {
    margin: 40px;
  }
  ul {
    width: 100%;
    @media (min-width: 1000px) {
      width: 40vw;
    }
    li {
      display: flex;
      align-items: center;
      margin-bottom: 25px;
      @media (min-width: 1000px) {
        margin-bottom: 15px;
      }
      .product {
        position: relative;
        left: 25px;
        width: 100px;
        height: 100px;
        border-radius: 50%;
      }
    }
  }
  button {
    position: relative;
    right: 16px;
    background-color: white;
    border-radius: 50%;
    border: none;
    width: 35px;
    height: 35px;
    -webkit-box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    -moz-box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    @media (min-width: 1000px) {
      width: 50px;
      height: 50px;
      right: 25px;
    }
    img {
      width: 35px;
      height: 35px;
      @media (min-width: 1000px) {
        width: 50px;
        height: 50px;
      }
    }
  }

  .pre-info {
    width: 100%;
    max-width: 250px;
    background: rgba(101, 163, 174, 0.2);
    padding-left: 40px;
    padding-right: 30px;
    border-top-right-radius: 15px;
    border-bottom-right-radius: 15px;
    @media (min-width: 1000px) {
      width: 250px;
    }
    h5 {
      font-size: 20px;
      margin-top: 5px;
      margin-bottom: 5px;
      font-style: normal;
      font-weight: bold;
      @media (min-width: 1000px) {
        font-size: 22px;
      }
    }
    p {
      margin-top: 5px;
      font-style: normal;
      font-weight: 400;
      opacity: 0.5;
      font-size: 12px;
      @media (min-width: 1000px) {
        font-weight: 500;
        font-size: 16px;
      }
    }
  }

}
</style>
