<template>
  <div class="container">
    <part1/>
    <poster/>
    <part3/>
  </div>
</template>

<script>
import part1 from '~/layouts/soluciones/part1.vue'
import part2 from '~/layouts/soluciones/part2.vue'
import part3 from '~/layouts/soluciones/part3.vue'
import poster from '~/layouts/soluciones/poster.vue'
import processIntro from '~/layouts/home/process.vue'

export default {
  components: {
    part1,
    part2,
    part3,
    poster
  }
}
</script>

<style lang="scss" scoped>
  .container {
    margin-top: 75px;
    background-color: #f0f6f7;
    overflow: visible;
    @media (min-width: 1000px) {
      margin-top: 100px;
    }
  }
</style>
