<template>
    <div id="service-list">
      <!-- <img class="parallax-background" v-rellax="{speed: -10, vertical: true, horizontal: false}" src="../../assets/images/Soluciones/bg-clear.png" alt=""> -->
      <nuxt-link class="service-content" to="/marcas/neugart">
        <div class="image">
          <img src="@/assets/images/marcas/neugart.png">
        </div>
        <!-- <div class="text">
          <div class="title">
          <h2>Neugart</h2>
          </div>
        </div> -->
      </nuxt-link>
      <nuxt-link class="service-content" to="/marcas/rw">
        <div class="image">
          <img src="@/assets/images/marcas/RW_logo.svg">
        </div>
      </nuxt-link>
      <nuxt-link class="service-content" to="/marcas/siemens">
        <div class="image">
          <img src="@/assets/images/marcas/siemens.png">
        </div>
      </nuxt-link>
      <nuxt-link class="service-content" to="/marcas/zimm">
        <div class="image">
          <img src="@/assets/images/marcas/zimm.png">
        </div>
      </nuxt-link>
      <nuxt-link class="service-content" to="/marcas/festo">
        <div class="image">
          <img src="@/assets/images/marcas/festo.png">
        </div>
      </nuxt-link>
      <nuxt-link class="service-content" to="/marcas/weiss-robotics">
        <div class="image">
          <img src="@/assets/images/marcas/weiss.png">
        </div>
      </nuxt-link>
    </div>

</template>

<script>
import defaultValues from '~/assets/text/categorias-prod.json'

export default {
  data() {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>
  #service-list {
    display: grid;
    grid-template-columns: 1fr;
    height: auto;
    width: 90%;
    margin-left: 5%;
    margin-right: 5%;
    align-self: flex-end;
    position: relative;
    @media (min-width: 700px) {
      grid-template-columns: 47.5% 47.5%;
      grid-column-gap: 5%;
      width: 80%;
      margin-left: 10%;
      margin-right: 10%;
    }
    @media (min-width: 1000px) {
      grid-template-columns: 31.6% 31.6% 31.6%;
      grid-column-gap: 2.5%;
    }
    .parallax-background {
      width: 100%;
      position: absolute;
      z-index: 1;
    }
    a {
      text-decoration: none;
    }
  }
  .service-content {
    transition: 0.5s;
    border: 1px solid rgba(#CCCCCC, 0.4);
    width: 100%;
    //min-height: 60vh;
    display: block;
    z-index: 5;
    //background: rgba(#CCCCCC, 0.4);
    margin-top: 25px;
    &:hover {
      background-color: rgba(#CCCCCC, 0.4);
    }
    .text {
      bottom: 0;
      text-align: left;
      padding-left: 5%;
      padding-right: 5%;
      display: flex;
      flex-flow: column;
      justify-content: center;
      align-items: flex-start;
      .title {
        margin-left: 0;
        margin-right: 0;
        border-color: black;
        h2 {
          transition: 0.5s;
          border-color: black;
          //color: #65A3AE;
          color: black;
          line-height: 1.7rem;
          text-decoration: none;
          @media (max-width: 400px) {
            font-size: 30px;
          }
        }
      }
      p {
        line-height: 1.5;
        color: #87888a;
        text-align: justify;
        margin: 0;
        height: 0;
        overflow: hidden;
      }
    }
    .image {
      min-height: 250px;
      height: 20vh;
      width: 95%;
      overflow: hidden;
      margin: auto;
      padding-left: 2.5%;
      padding-right: 2.5%;
      // @media (min-width: 700px) {
      //   width: 85%;
      //   margin: auto auto;
      // }
      img {
        transition: transform 1s ease;
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }
  }
  // .service-content:nth-child(2n) {
  //   .text {
  //     text-align: left;
  //     align-items: flex-start;
  //     @media (min-width: 700px) {
  //       grid-column: 2 / 3;
  //     }
  //   }
  //   .image {
  //     @media (min-width: 700px) {
  //       grid-column: 1 / 2;
  //       grid-row: 1;
  //     }
  //   }
  // }

</style>
