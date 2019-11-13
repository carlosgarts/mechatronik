<template>
  <div class="container">
    <div id="tester">

    </div>
    <!-- {{item.scrollHeight}} -->
    <intro/>
    <bannerB/>
    <sliderIntro/>
    <cifras/>
    <processIntro/>
    <mail/>
    <!-- <div id="test" class="credit">
      <a href="https://www.script-angels.com">Web Development by Carlos Gamez</a>
    </div> -->
  </div>
</template>

<script>
import intro from '~/layouts/home/intro.vue'
import bannerB from '~/layouts/home/banner.vue'
import sliderIntro from '~/layouts/home/slider.vue'
import cifras from '~/layouts/home/cifras.vue'
import processIntro from '~/layouts/home/process.vue'
import mail from '~/layouts/home/mail.vue'

// if (process.client) {
//   var nav = document.getElementById('tester');
//   console.log('nav is ' + nav);
// }

export default {
  components: {
    intro,
    sliderIntro,
    bannerB,
    cifras,
    processIntro,
    mail
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

  .VueCarousel-pagination {
    position: absolute;
    z-index: 5;
    bottom: 20px;
  }
</style>
