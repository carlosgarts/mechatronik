<template>
  <div class="container">
    <div id="tester">

    </div>
    <!-- <sliderIntro/> -->
    <!-- {{item.scrollHeight}} -->
    <intro/>
    <!-- <bannerB/> -->
    <div class="margin-container">
      <blogWidget/>
      <productWidget/>
    </div>
    <div class="margin-container">
      <serviciosWidget/>
    </div>
    <div class="full-container color">
      <solucionesWidget/>
    </div>
    <div class="margin-container">
      <exitosWidget/>
    </div>
    <div class="full-container bw">
      <marcasWidget/>
    </div>
    <!-- <cifras/> -->
    <!-- <processIntro/> -->
    <!-- <mail/> -->
    <!-- <div id="test" class="credit">
      <a href="https://www.script-angels.com">Web Development by Carlos Gamez</a>
    </div> -->
  </div>
</template>

<script>
import intro from '~/layouts/home/intro.vue'
// import bannerB from '~/layouts/home/banner.vue'
import productWidget from '~/layouts/products/products-widget.vue'
import blogWidget from '~/layouts/blog/blog-widget.vue'
import serviciosWidget from '~/layouts/servicios/servicios-widget.vue'
import solucionesWidget from '~/layouts/soluciones/soluciones-widget.vue'
import sliderIntro from '~/layouts/home/slider.vue'
import exitosWidget from '~/layouts/exitos/exitos-widget.vue'
import marcasWidget from '~/layouts/marcas/marcas-widget.vue'
// import cifras from '~/layouts/home/cifras.vue'
// import processIntro from '~/layouts/home/process.vue'
// import mail from '~/layouts/home/mail.vue'

// if (process.client) {
//   var nav = document.getElementById('tester');
//   console.log('nav is ' + nav);
// }

export default {
  components: {
    intro,
    productWidget,
    blogWidget,
    sliderIntro,
    serviciosWidget,
    solucionesWidget,
    exitosWidget,
    marcasWidget
    // bannerB,
    // cifras,
    // processIntro,
    // mail
  },
  data: function () {
    return {
      item: "None"
    }
  },
  // mounted () {
  //   if (process.browser) {
  //     this.item = document.getElementById("test");
  //     console.log(window);
  //   }
  // },
}
</script>

<style lang="scss">

  .container {
    overflow: hidden;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

  .credit {
    color: white;
    width: 100%;
    text-align: center;
    margin: 10px;
    a {
      color: gray;
      text-decoration: none;
      opacity: 0.3;
    }
  }

  // .VueCarousel-pagination {
  //   position: absolute;
  //   z-index: 5;
  //   bottom: 20px;
  // }

  .VueCarousel-navigation-button {
    font-size: 20px;
    @media (min-width: 700px) {
      font-size: 50px;
    }
  }

  .margin-container {
    width: 90%;
    max-width: 1200px;
    @media (min-width: 900px) {
      width: 80%;
    }
  }
  .full-container {
    width: 100%;
    padding: 50px 5%;
    @media (min-width: 900px) {
      padding: 25px 10%;
    }
    &.color {
      background: #65A3AE;
      background: -webkit-linear-gradient(to right, #005578, #65A3AE);
      background: linear-gradient(to right, #005578, #65A3AE);
    }
    &.bw {
      margin-top: 30px;
      background: rgba(gray, 0.2);
    }
  }
</style>
