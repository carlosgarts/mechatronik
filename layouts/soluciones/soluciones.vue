<template>
    <div id="solution-list">
      <img class="parallax-background" v-rellax="{speed: -10, vertical: true, horizontal: false}" src="../../assets/images/Soluciones/bg-clear.png" alt="">
      <div class="solution-content" v-scroll-reveal.reset v-for="solution in solutions">
        <div class="text">
          <div class="tbb">
          <h2><strong>{{solution.titulo}}</strong></h2>
          </div>
          <p v-html="solution.descripcion"></p>
        </div>
        <div class="image">
          <img :src="solution.fotos">
        </div>
      </div>
    </div>

</template>

<script>

export default {
  data() {
    return {
      solutions: [1,2,3,4],
      isLoading: true
    }
  },
  mounted: async function() {
      try {
        var Solutions = await this.$axios.get('https://system.mechatronik-group.com/api/soluciones');
        this.solutions = Solutions.data.soluciones;
        this.isLoading = false;
      } catch (e) {
        this.isLoading = false;
        console.log(e);
      }
  }
}
</script>

<style lang="scss" scoped>
  #solution-list {
    height: auto;
    width: 100vw;
    align-self: flex-end;
    position: relative;
    .parallax-background {
      width: 100%;
      position: absolute;
      z-index: 1;
    }
  }
  .solution-content {
    width: 100%;
    min-height: 60vh;
    display: grid;
    grid-template-columns: 1fr;
    z-index: 5;
    position: relative;
    margin-top: 50px;
    margin-bottom: 100px;
    @media (min-width: 700px) {
      grid-template-columns: 1fr 1fr;
    }
    .text {
      text-align: right;
      padding-left: 7.5%;
      padding-right: 7.5%;
      display: flex;
      flex-flow: column;
      justify-content: center;
      align-items: flex-end;
      .tbb {
        margin-left: 0;
        margin-right: 0;
        border-color: black;
        h2 {
          transition: 0.5s;
          color: black;
          border-color: black;
          @media (max-width: 400px) {
            font-size: 30px;
          }
        }
      }
      p {
        line-height: 1.5;
      }
    }
    .image {
      height: 300px;
      width: 85%;
      overflow: hidden;
      margin: auto;
      margin-top: 20px;
      @media (min-width: 700px) {
        height: 85%;
        width: 85%;
        margin: auto auto;
      }
      img {
        transition: transform 10s ease;
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
      img:hover {
        transform: scale(1.3);
      }
    }
  }
  .solution-content:nth-child(2n) {
    .text {
      text-align: left;
      align-items: flex-start;
      @media (min-width: 700px) {
        grid-column: 2 / 3;
      }
    }
    .image {
      @media (min-width: 700px) {
        grid-column: 1 / 2;
        grid-row: 1;
      }
    }
  }

</style>
