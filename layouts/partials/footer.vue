<template>
  <footer>
    <div class="ft-grid">
      <div class="column">
        <h2>Mechatronik Lösungen</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
          tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
          quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </p>
      </div>
      <div class="column" id="contact">
        <h2>Contact Us</h2>
        <ul>
          <li><img class="icon" src="@/assets/images/SVG/mail.svg">email: info@mechatronik.com</li>
          <li><img class="icon" src="@/assets/images/SVG/call.svg">tel. +51 1 (81) 59 98 01 98</li>
          <li><img class="icon" src="@/assets/images/SVG/call.svg">cel. +52 1 (81) 20 40 28 15</li>
          <li><img class="icon" src="@/assets/images/SVG/location.svg"><div><a href="https://www.google.com/maps/place/IOS+OFFICES+Arboleda/@25.6495432,-100.3569827,20.5z/data=!4m5!3m4!1s0x8662bde757081d17:0x6a1251648727527f!8m2!3d25.6495863!4d-100.3568052">Mechatronik Group | Ave. Roble No. 660 Piso 3 Col. Valle del Campestre | San Pedro Garza Garcia, N.L. Mexico | CP. 66265</a></div> </li>
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
  background-color: #000;
  width: 100%;
  min-height: 300px;
  font-size: 14px;
  line-height: 2.1;
  font-family: Raleway, Roboto, Arial, sans-serif;
  margin-top: 5%;
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
  column-gap: 5%;
  margin-left: 5%;
  margin-right: 5%;
  @media (min-width: 600px) {
    grid-template-columns: 1fr 1fr 1fr;
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
  margin: 5%;
  margin-bottom: 0;
  padding-bottom: 25px;
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
