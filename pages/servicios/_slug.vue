<template>
  <div class="container">
      <ServiciosReader/>

      <!-- <div class="three-items">
              <div class="item">
                <img src="https://blog.mechatronik-group.com/wp-content/uploads/2020/03/csm_MOTEK_NEUGART-011_4e0be68990.jpg" alt="image">
                <h3>Analizar y evaluar la disponibilidad tecnológica de los sistemas operativos de su empresa</h3>
                <p>Le ayudamos a comprender exactamente donde se encuentran desde un punto de vista tecnológico.
                  Traemos a su atención sus partes más débiles y menos flexibles, aquellos que podrían poner a su empresa en riesgo de
                  interrupción en el futuro cercano. </p>
              </div>
              <div class="item">
                <img src="https://blog.mechatronik-group.com/wp-content/uploads/2020/03/csm_Neugart-Motek-Booth-4_83878597ab.jpg" alt="image">
                <h3>Innove su mercado</h3>
                <p>En Mechatronik Lösungen no vendemos soluciones que pretenden decirle como debe administrar u operar su negocio.
                  Si tiene una visión sobre como quiere hacerlo, donde debe fortalecerse y ser más competitivo o cuales son sus
                  puntos más débiles que debe cubrir, el equipo de consultoría Industry 4.0 se basará en esta visión y creará
                  rápidamente una tecnología adecuada a su infraestructura y su visión </p>
              </div>
              <div class="item">
                <img src="https://blog.mechatronik-group.com/wp-content/uploads/2020/03/7837-03_Wasser_Visual_180205-1_sRGB2.jpg" alt="image">
                <h3>Digitalizar su negocio de forma sostenible</h3>
                <p>La mayoría de las empresas que encontramos en nuestro negocio cotidiano apenas han completado
                  ( o incluso comenzado) una transición a la industria 3.0. Para llegar a un estado en el que su empresa pueda adaptarse a
                  los cambios disruptivos, primero debe digitalizar e integrar completamente sus sistemas comerciales.
                  No se trata solo de integrarse, si no también de como se implementa esa integraci</p>
              </div>
            </div> -->

  </div>
</template>

<script>
import ServiciosReader from '~/layouts/servicios/servicios-reader.vue'

export default {
  components: {
    ServiciosReader
  }
}
</script>

<style lang="scss">

  .format {
    line-height: 1.5;
    li, p {
      transition: 0.5;
      font-size: 0.8rem;
      @media(min-width: 800px) {
        font-size: 1rem;
      }
    }
    img {
      width: 100%;
    }
  }

  .servicios2 {
    padding: 0;
    list-style: none;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-column-gap: 15px;
    grid-row-gap: 15px;
    @media(min-width: 700px) {
      grid-template-columns: 1fr 1fr 1fr;
    }
    @media(min-width: 900px) {
      grid-template-columns: 1fr 1fr 1fr 1fr;
    }
    @media(min-width: 1100px) {
      grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    }
    li {
      background: #BBBDC0;
    }
    a {
      text-decoration: none;
      color: black;
      p {
        margin-left: 10px;
        margin-right: 10px;
        font-size: 0.8rem;
      }
    }
    img {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }
  }

  .wp-block-columns {
    display: grid;
    grid-template-columns: 1fr;
    grid-column-gap: 25px;
    margin-bottom: 80px;
    @media(min-width: 800px) {
      grid-template-columns: 1fr 1fr;
    }
    .wp-block-image {
      width: 100%;
      height: 100%;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .wp-block-column {
      h3 {
        transition: 0.5s;
        text-align: left;
        color: #2d373c;
        margin-bottom: 25px;
        font-size: 1.25rem;
        @media(min-width: 800px) {
          font-size: 1.625rem;
        }
        &.medium-important-title {
          color: white;
        }
      }
    }
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
  .color-background {
    width: 140%;
    margin: 80px -20%;
    padding: 5% 20%;
    background: #65A3AE;
    background: -webkit-linear-gradient(to right, #005578, #65A3AE);
    background: linear-gradient(to right, #005578, #65A3AE);
    color: white;
    .medium-important-title, .important-title {
      color: white;
      text-align: left;
    }
    li {
      margin-bottom: 10px;
      list-style: none;
      position: relative;
      strong {
        color: #ffb900;
      }
    }
    li::before {
      color: #ffb900;
      content: "\203A";
      /* Unicode of character to precede the list item */
      display: inline-block;
      font-size: 1.5em;
      /* use em or % */
      left: -1.1225em;
      /* use em, line up bullet flush with left hand side */
      position: absolute;
      /* Set the bullet positioned absolutely top left */
      top: -.4em;
    }
  }
  .important-title {
    transition: 0.5s;
    font-size: 1.8rem;
    margin-top: 0;
    @media(min-width: 800px) {
      font-size: 3rem;
    }
  }
  .medium-important-title {
    transition: 0.5s;
    font-size: 1.8rem;
    margin-top: 0;
    @media(min-width: 800px) {
      font-size: 1.8rem;
    }
  }
  .grad-title {
    transition: 0.5;
    font-size: 1.8rem;
    height: 3em;
    text-align: center;
    background: -webkit-linear-gradient(to right, #005578, #65A3AE);
    background: linear-gradient(to right, #005578, #65A3AE);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    @media (min-width: 800px) {
      font-size: 3rem;
    }
  }
  .three-items {
    display: grid;
    width: 100%;
    grid-template-columns: 1fr;
    grid-column-gap: 15px;
    grid-row-gap: 15px;
    height: auto;
    overflow: hidden;
    @media (min-width: 600px) {
      grid-template-columns: 1fr 1fr;
    }
    @media (min-width: 800px) {
      grid-template-columns: 1fr 1fr 1fr;
    }
    .item {
      width: 100%;
      background-color: #EBF0F5;
      margin-bottom: 30px;
      img {
        height: 250px;
        object-fit: cover;
      }
      h3 {
        text-align: left;
        margin: 15px;
        color: black;
        font-weight: bold;
      }
      p {
        margin: 15px;
      }
    }
  }
</style>
