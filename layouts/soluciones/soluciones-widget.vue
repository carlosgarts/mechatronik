<template>
  <div class="section">
    <div id="solutions-widget">
      <h3>Soluciones</h3>
      <p>
        Nuestras soluciones están basadas en nuestra experiencia durante el
        ciclo de desarrollo, desde la definición de requisitos hasta la
        integración de sistemas y validación de sistemas mecatrónicos con una
        densidad de potencia optima y alta confiabilidad, nuestros ingenieros
        tienen experiencia en el desarrollo de un sistema altamente dinámico
        en control de movimiento.
      </p>
      <div class="solutions">
        <div class="info">
          <ul>
            <li v-for="solution in solutions" :key="solution.id">
              <nuxt-link :to="'/soluciones/'+ solution.slug">
                <h4>&#10095 {{solution.title.rendered}}</h4>
              </nuxt-link>
            </li>
          </ul>
        </div>
        <div class="image">
          <img src="@/assets/images/Soluciones/machine.png" alt="">
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      solutions: []
    }
  },
  mounted: async function() {
      try {
        var Servs = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=19');
        this.solutions = Servs.data;
      } catch (e) {
        console.log(e);
      }
  }
}
</script>

<style lang="scss" scoped>

  .section {
    display: block;
    min-height: auto;
    color: white;
    text-align: left;
  }

  .solutions {
    display: grid;
    width: 100%;
    grid-template-columns: 1fr;
    grid-row-gap: 100px;
    @media (min-width: 800px) {
      grid-template-columns: 1fr 1fr;
    }
  }

  ul {
    list-style: none;
    padding: 0;
    width: 100%;
    @media (min-width: 1000px) {
      width: 80%;
    }
    li {
      transition: 0.5s;
      border-bottom: 1px solid gray;
      &:nth-child(1) {
        border-top: 1px solid gray;
      }
      &:hover {
        //background-color: rgba(gray, 0.5);
      }
    }
    a {
      color: #ffb900;
      text-decoration: none;
      &:hover {
        text-decoration: underline;
      }
    }
  }


.card:hover {
  .card-cover {
    img {
      transform: scaleX(105%) scaleY(105%);
    }
  }
  }

  #solutions-widget {
    display: block;

    @media (min-width: 800px) {

    }
    @media (min-width: 1100px) {

    }
    h3 {
      color: white;
      text-align: left;
      letter-spacing: 0px;
      font-style: normal;
      font-weight: normal;
      font-size: calc(35px + (50 - 35) * ((100vw - 300px) / (1600 - 300)));
      margin-bottom: 10px;
    }
  }

  .solutions {
    .info {
      height: 100%;
    }
    .image {
      width: 100%;
      max-height: 400px;
      img {
        height: 100%;
      }
    }
  }

</style>
