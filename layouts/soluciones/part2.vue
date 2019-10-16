<template>
  <div class="section">
    <div id="soluciones--2">
      <div class="fabricacion">
        <div class="frame">
          <div class="content">
            <div class="title">
              <div class="ampersand">&</div>
              <h5>Diseño<br>Fabricación </h5>
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

          <img class="adapt-img" src="https://i2.wp.com/bmmetalroofing.com/wp-content/uploads/2016/01/test.jpg?w=800" alt="ingenieria">
        </div>
        <div class="side-tag"> <span>&#9472&#9472&#9472</span> Soluciones</div>
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
}
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
