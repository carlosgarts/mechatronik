<template>
  <footer>
    <div class="ft-grid">
      <div class="column">
        <h2>Mechatronik</h2>
        <p>
          Dedicados a una excelente atención al cliente en productos, servicios y una solución para la industria.
          Ya sea para un posicionamiento preciso y repetibe, velocidad constante y alto movimiento dinámico,
          largas trayectoria de desplazamiento o cambios rápidos de velocidad. <br>
          Tenemos una cartera de servos, reductores planetarios, actuadores lineales y más para la solución óptima
          para cada tarea de control de movimiento. <br>
          Contamos con un amplio conjunto de servicios y experiencia en la ingeniería de automatización
          e integracion de nuevas tecnologías.
        </p>
      </div>
      <div class="column" id="contact">
        <h2>Contact Us</h2>
        <ul>
          <li><img class="icon" src="@/assets/images/SVG/mail.svg">email: info@mechatronik-group.com</li>
          <!-- <li><img class="icon" src="@/assets/images/SVG/call.svg">tel. +51 1 (81) 59 98 01 98</li> -->
          <li><img class="icon" src="@/assets/images/SVG/call.svg">cel. +52 1 (81) 20 40 28 15</li>
          <li><img class="icon" src="@/assets/images/SVG/location.svg"><div><a href="https://goo.gl/maps/dqL6NEvXCiKuQKMa9">Mechatronik Group | Ave. Roble No. 660 Piso 3 Col. Valle del Campestre | San Pedro Garza Garcia, N.L. Mexico | CP. 66265</a></div> </li>
        </ul>
      </div>
      <div class="column">
        <h2>Follow Us</h2>
        <div class="social-block">
          <a class="social" href="https://www.instagram.com/mechatronik_group/"><img src="@/assets/images/SVG/instagram.svg"></a>
          <a class="social" href="https://www.youtube.com/channel/UCe2vgrkb6UAQSezAuz28sUQ/"><img src="@/assets/images/SVG/youtube.svg"></a>
          <a class="social" href="https://www.linkedin.com/company/33520557"><img src="@/assets/images/SVG/linkedin.svg"></a>
        </div>
      </div>
    </div>
    <p class="credits">@2019 Mechatronik All Rights Reserved. <a href="#">Web development by Carlos Gamez</a></p>
  </footer>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
footer {
  color:#fff;
  text-align: center;
  background-color: #3f3f3f;
  width: 100%;
  min-height: 300px;
  font-size: 12px;
  line-height: 2.1;
  font-family: Raleway, Roboto, Arial, sans-serif;
  //margin-top: 5%;
  z-index: 5;
  position: relative;
}
ul {
  padding-left: 0;
  li {
    list-style-type: none;
    display: grid;
    grid-template-columns: auto 1fr;
    grid-column-gap: 5%;
    margin-bottom: 10px;
    text-align: justify;
  }
}

.ft-grid {
  display: grid;
  grid-template-columns: 1fr;
  column-gap: 7.5%;
  margin-left: 7.5%;
  margin-right: 7.5%;
  @media (min-width: 600px) {
    grid-template-columns: 1fr 1fr 1fr;
    column-gap: 5%;
    margin-left: 5%;
    margin-right: 5%;
  }
  .column {
    text-align: center;
    display: flex;
    flex-flow: column;
    @media (min-width: 600px) {
      text-align: justify;
    }
    p {
      text-align: justify;
    }
  }
}

.icon {
  width: 20px;
  display: block;
  margin-top: 5px;
}

.credits {
  margin: 7.5%;
  margin-bottom: 0;
  padding-bottom: 25px;
  margin-top: 40px;
  a {
    text-decoration: underline;
  }
}

a {
  color: white;
  text-decoration: none;
}

.social-block {
  display: flex;
  width: 100%;
  justify-content: space-between;
  flex-flow: wrap;
  @media (min-width: 600px) {
    max-width: 250px;
  }
}

.social {
  background-color:  #65a3ae;
  height: 70px;
  width: 70px;
  padding: 10px;
  border-radius: 50%;
  img {
    height: 100%;
    width: 100%;
  }
}
</style>
