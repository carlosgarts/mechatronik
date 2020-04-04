<template>
    <div id="service-list">
      <!-- <img class="parallax-background" v-rellax="{speed: -10, vertical: true, horizontal: false}" src="../../assets/images/Soluciones/bg-clear.png" alt=""> -->
      <nuxt-link class="service-content" :to="'/servicios/'+ service.slug" v-for="service in services">
        <div class="image">
          <img :src="service.featured_image_url">
        </div>
        <div class="text">
          <div class="title">
          <h2><strong>{{service.title.rendered}}</strong></h2>
          </div>
          <p v-html="service.excerpt.rendered"></p>
        </div>
      </nuxt-link>
    </div>

</template>

<script>
import defaultValues from '~/assets/text/servicios.json'

export default {
  data() {
    return {
      services: defaultValues.data,
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
        var Services = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=18');
        this.services = Services.data;
        this.isLoading = false;
        console.log(this.services);
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
  }
  .service-content {
    background-color: rgba(204, 204, 204, 0.4);;
    text-decoration: none;
    border: 1px solid #CCCCCC;
    width: 100%;
    display: block;
    z-index: 5;
    position: relative;
    margin-top: 25px;
    border: 1px solid rgba(204, 204, 204, 0.4);
    .text {
      //position: absolute;
      bottom: 0;
      text-align: left;
      padding-left: 7.5%;
      padding-right: 7.5%;
      display: flex;
      flex-flow: column;
      justify-content: center;
      align-items: flex-start;
      //background: rgb(101,163,174);
      //background: linear-gradient(0deg, rgba(101,163,174,0.9080766095500701) 37%, rgba(255,255,255,0) 100%);
      .title {
        margin-left: 0;
        margin-right: 0;
        border-color: black;
        h2 {
          transition: 0.5s;
          border-color: black;
          //color: #65A3AE;
          color: black;
          line-height: 2rem;
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
      min-height: 300px;
      height: 30vh;
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
