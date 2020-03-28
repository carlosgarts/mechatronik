<template>
  <div class="container">
      <ServiciosReader/>
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
</style>
