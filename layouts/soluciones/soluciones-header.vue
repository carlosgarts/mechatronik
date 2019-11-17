<template>
  <div class="section">
    <div class="title--bar">
      <div class="tbb">
        <h2><strong>SOLUCIONES</strong></h2>
      </div>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
.section {
  min-height: 400px;
}

.title--bar {
  display: block;
  width: 100%;
  background: url('../../assets/images/Soluciones/fondo-1.jpg') no-repeat;
  background-size: cover;
  background-attachment: fixed;
  margin-top: 100px;
  height: auto;
  display: flex;
  flex-flow: column;
  align-items: flex-start;
  justify-content: center;
  @media (min-width: 1000px) {
    margin-top: 140px;
  }
  p {
    color: white;
    line-height: 1.5;
    margin-left: 10%;
    margin-right: 10%;
    text-align: left;
    margin-bottom: 50px;
    @media (min-width: 1000px) {
      margin-left: 5%;
      margin-right: 5%;
    }
  }
  .tbb {
    margin-top: 10%;
    margin-left: 10%;
    margin-right: 10%;
    @media (min-width: 1000px) {
      margin-top: 0;
      margin-left: 5%;
      margin-right: 5%;
    }
    h2 {
      font-size: calc(32px + (70 - 32) * ((100vw - 300px) / (1600 - 300)));
      font-family: Raleway;
      font-style: normal;
      font-weight: 400;
    }
  }
}
</style>
