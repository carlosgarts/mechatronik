<template>
    <div class="banner">
      <h1 v-scroll-reveal.reset >"OUR SOLUTIONS FOR YOUR VISION" | mechatronik</h1>
    </div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
  .banner {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: black;
    height: 20vh;
    h1 {
      font-family: Raleway;
      font-style: normal;
      font-weight: bold;
      font-size: 35px;
      font-size: calc(18px + (45 - 18) * ((100vw - 300px) / (1600 - 300)));
      line-height: 96.4%;

      /* or 34px */
      text-transform: uppercase;

      color: #FFFFFF;
    }
  }

</style>
