<template>
  <div class="section">
    <div id="services-widget">
      <h3>Casos de Éxito</h3>
      <div class="services-slider">
        <carousel :perPageCustom="[[50, 1], [700, 2], [1000, 3]]" :paginationEnabled="true" :navigationEnabled="true" navigationNextLabel="&#10095" navigationPrevLabel="&#10094" paginationActiveColor="#65A3AE">
          <slide v-for="service in services" :key="service.id">
            <div class="card">
              <nuxt-link :to="'/servicios/'+ service.slug">
              <div class="card-cover">
                <img :src="service.featured_image_url">
              </div>
              <div class="card-text">
                <h4><strong>{{service.title.rendered}}</strong></h4>
                <p v-html="service.excerpt.rendered"></p>
              </div>
              </nuxt-link>
            </div>
          </slide>
        </carousel>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      services: []
    }
  },
  mounted: async function() {
      try {
        var Servs = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=43');
        this.services = Servs.data;
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
  }

  .services-slider {
    display: block;
    width: 100%;
  }

  .card {
    transition: 0.5s;
    width: 95%;
    height: 100%;
    margin: 0 2.5%;
    border: 1px solid #CCCCCC;
    a {
      text-decoration: none;
    }
    .card-cover {
      width: 100%;
      height: 250px;
      overflow: hidden;
      img {
        transition: transform 1s;
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }

    .card-text {
      text-align: left;
      margin: 30px;
      margin-top: 37px;
      h4 {
        color: #65A3AE;
        font-size: 21px;
        line-height: 1.25rem;
        margin-top: 0;
        margin-bottom: 15px;
      }
      p {
        color: #87888a;
        line-height: 1.5;
        text-align: justify;
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

  #services-widget {
    display: block;
    margin: 32px 0;
    @media (min-width: 800px) {

    }
    @media (min-width: 1100px) {

    }
    h3 {
      color: black;
      text-align: left;
      letter-spacing: 0px;
      font-style: normal;
      font-weight: normal;
      font-size: calc(35px + (50 - 35) * ((100vw - 300px) / (1600 - 300)));
      margin-bottom: 30px;
    }
  }

</style>
