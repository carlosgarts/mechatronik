<template>
    <div class="title--bar">
      <div class="title--content">
        <div class="nav-history"><a href="https://mechatronik-group.com/">Inicio</a> &#10095 Blog</div>
        <h2>Entradas Recientes</h2>
      </div>
    </div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>

.title--bar {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  background-color: white;
  background-size: cover;
  background-attachment: fixed;
  height: auto;

}

.title--content {
  width: 80%;
  margin: 45px 0;
  .nav-history {
    margin: 0;
  }
  h2 {
    font-size: calc(35px + (45 - 35) * ((100vw - 300px) / (1600 - 300)));
    font-style: normal;
    font-weight: normal;
  }
}
</style>
