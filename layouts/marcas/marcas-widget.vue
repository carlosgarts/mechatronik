<template>
  <div class="section">
    <div id="marcas-widget">
      <div class="marcas-list">
        <nuxt-link class="brand" to="/marcas/festo">
          <img src="@/assets/images/marcas/festo.png" alt="Festo">
        </nuxt-link>
        <nuxt-link class="brand" to="/marcas/neugart">
          <img src="@/assets/images/marcas/neugart.png" alt="Neugart">
        </nuxt-link>
        <nuxt-link class="brand" to="/marcas/siemens">
          <img src="@/assets/images/marcas/siemens.png" alt="Siemens">
        </nuxt-link>
        <nuxt-link class="brand" to="/marcas/zimm">
          <img src="@/assets/images/marcas/zimm.png" alt="Zimm">
        </nuxt-link>
        <nuxt-link class="brand" to="/marcas/rw">
          <img src="@/assets/images/marcas/RW_logo.svg" alt="RW">
        </nuxt-link>
        <nuxt-link class="brand" to="/marcas/weiss-robotics">
          <img src="@/assets/images/marcas/weiss.png" alt="Weiss Robotics">
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      marcas: []
    }
  }
}
</script>

<style lang="scss" scoped>

  .section {
    display: block;
    min-height: auto;
  }

  .marcas-list {
    display: flex;
    width: 100%;
    flex-wrap: wrap;
    justify-content: space-around;
    .brand {
      width: 30%;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 15px;
      img {
        transition: 0.5s;
        width: 100%;
        filter: grayscale(1);
        &:hover {
          filter: grayscale(0);
        }
      }
      @media (min-width: 800px) {
        width: 13%;
        margin: 0;
      }
    }
  }

  .card {
    transition: 0.5s;
    width: 95%;
    height: 100%;
    margin: 0 2.5%;
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
      text-align: center;
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

  #marcas-widget {
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
