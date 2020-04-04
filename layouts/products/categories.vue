<template>
    <div id="service-list">
      <!-- <img class="parallax-background" v-rellax="{speed: -10, vertical: true, horizontal: false}" src="../../assets/images/Soluciones/bg-clear.png" alt=""> -->
      <nuxt-link class="service-content" :to="'/categorias/'+ categorie.slug" v-for="categorie in categories">
        <div class="image">
          <img :src="categorie.image.src">
        </div>
        <div class="text">
          <div class="title">
          <h2>{{categorie.name}}</h2>
          </div>
          <p v-html="categorie.description"></p>
        </div>
      </nuxt-link>
    </div>

</template>

<script>
import defaultValues from '~/assets/text/categorias-prod.json'

export default {
  data() {
    return {
      categories: defaultValues.data,
      isLoading: true
    }
  },
  // mounted: async function() {
  //     try {
  //       var Services = await this.$axios.get('https://system.mechatronik-group.com/api/servicios');
  //       this.services = Services.data.servicios;
  //       this.isLoading = false;
  //     } catch (e) {
  //       this.isLoading = false;
  //       console.log(e);
  //     }
  // },
  mounted: async function() {
      try {
        var Categories = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products/categories?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f');
        this.categories = Categories.data;
        this.isLoading = false;
        console.log(this.categories);
      } catch (e) {
        this.isLoading = false;
        console.log(e);
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
    border: 1px solid rgba(#CCCCCC, 0.4);
    width: 100%;
    //min-height: 60vh;
    display: block;
    z-index: 5;
    background: rgba(#CCCCCC, 0.4);
    margin-top: 25px;
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
      width: 100%;
      overflow: hidden;
      margin: auto;
      // @media (min-width: 700px) {
      //   width: 85%;
      //   margin: auto auto;
      // }
      img {
        transition: transform 1s ease;
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
      img:hover {
        transform: scale(1.3);
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
