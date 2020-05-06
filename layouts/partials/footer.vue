<template>
  <footer>
    <div class="ft-grid">
      <div class="column">
        <h2>Nosotros</h2>
        <p>
          Dedicados a una excelente atención al cliente. Contamos con una amplia cartera de productos
          para la solución óptima para cada tarea de control de movimiento asi como un conjunto de
          servicios y experiencia en la ingeniería de automatización e integracion de nuevas tecnologías.
          <!-- Ya sea para un posicionamiento preciso y repetibe, velocidad constante y alto movimiento dinámico,
          largas trayectoria de desplazamiento o cambios rápidos de velocidad. -->
        </p>
        <div class="social-block">
          <a class="social" href="https://www.instagram.com/mechatronik_group/"><img src="@/assets/images/SVG/instagram.svg" alt="social link"></a>
          <a class="social" href="https://www.youtube.com/channel/UCe2vgrkb6UAQSezAuz28sUQ/"><img src="@/assets/images/SVG/youtube.svg" alt="social link"></a>
          <a class="social" href="https://www.linkedin.com/company/33520557"><img src="@/assets/images/SVG/linkedin.svg" alt="social link"></a>
        </div>
      </div>
      <div class="column" >
        <h2>Quick Links</h2>
        <ul class="quick">
          <li><nuxt-link to="/productos">Productos <span>&#10095</span></nuxt-link></li>
          <li><nuxt-link to="/marcas">Marcas <span>&#10095</span></nuxt-link></li>
          <li><nuxt-link to="/categorias">Categorias <span>&#10095</span></nuxt-link></li>
          <li><nuxt-link to="/servicios">Servicios <span>&#10095</span></nuxt-link></li>
          <li><nuxt-link to="/soluciones">Soluciones <span>&#10095</span></nuxt-link></li>
          <li><nuxt-link to="/compañia">Compañia <span>&#10095</span></nuxt-link></li>
        </ul>
      </div>
      <div class="column" id="contact">
        <h2>Contáctanos</h2>
        <ul>
          <li><img class="icon" src="@/assets/images/SVG/mail.svg">Email: info@mechatronik-group.com</li>
          <!-- <li><img class="icon" src="@/assets/images/SVG/call.svg">tel. +51 1 (81) 59 98 01 98</li> -->
          <li><img class="icon" src="@/assets/images/SVG/call.svg">Cel. +52 1 (81) 20 40 28 15</li>
          <li><img class="icon" src="@/assets/images/SVG/location.svg"><div><a href="https://goo.gl/maps/dqL6NEvXCiKuQKMa9">Mechatronik Group | Ave. Roble No. 660 Piso 3 Col. Valle del Campestre | San Pedro Garza Garcia, N.L. Mexico | CP. 66265</a></div> </li>
        </ul>
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
  padding-top: 50px;
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
hr {
  width: 100%;
}
h2 {
  margin: 0;
  border-bottom: 1px solid gray;
}

.ft-grid {
  display: grid;
  grid-template-columns: 1fr;
  column-gap: 7.5%;
  margin-left: 5%;
  margin-right: 5%;
  @media (min-width: 800px) {
    grid-template-columns: 1fr 1fr 1fr;
    column-gap: 5%;
    margin-left: 10%;
    margin-right: 10%;
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
  position: relative;
  width: 100%;
  &:hover {
    text-decoration: underline;
  }
  span {
    position: absolute;
    right: 0;
  }
}

.quick {
  // display: flex;
  // flex-flow: column;
  li {
    display: flex;
  }
}

.social-block {
  display: flex;
  width: 100%;
  justify-content: flex-start;
  flex-flow: wrap;
  // @media (min-width: 600px) {
  //   max-width: 250px;
  // }
}

.social {
  transition: 0.5s;
  background: rgb(101,163,174);
  background: linear-gradient(45deg, rgba(101,163,174,1) 0%, rgba(132,218,233,1) 100%);
  height: 50px;
  width: 50px;
  margin-top: 10px;
  padding: 10px;
  margin-right: 10px;
  border-radius: 50%;
  opacity: 0.5;
  &:hover {
    opacity: 1;
  }
  img {
    height: 100%;
    width: 100%;
  }
}
</style>
