<template>
  <div class="flex-section">
    <div id="mailer">
      <mailer></mailer>
    </div>
  </div>
</template>

<script>
import mailer from '../partials/mailer.vue'
export default {
  components: {
    mailer
  }
}
</script>

<style lang="scss" scoped>

  #mailer {
    position: relative;
    width: 100%;
    -webkit-box-shadow: 10px 9px 17px -3px rgba(101,163,174,0.4);
    -moz-box-shadow: 10px 9px 17px -3px rgba(101,163,174,0.4);
    box-shadow: 10px 9px 17px -3px rgba(101,163,174,0.4);
    z-index: 15;
    @media (min-width: 350px) {
      width: 90%;
      margin-top: 10%;
    }
    @media (min-width: 500px) {
      width: 90%;
      bottom: 100px;
      margin-top: 0;
    }
    @media (min-width: 850px) {
      width: 70%;
    }
  }
</style>
