<template>
  <div class="socials">
    <social-sharing :url="url"
                      :title="titulo"
                      :description="titulo"
                      quote="Mechatronik Group, automatizacion y motion control"
                      hashtags="Mechatronik,automation,motion-control,automatizacion,tecnologia"
                      twitter-user="Mechatronik"
                      network-tag="content"
                      inline-template>
    <div class="social-list">
      <network network="facebook">
        <img src="@/assets/svg/facebook.svg" alt="Facebook">
      </network>
      <network network="linkedin">
        <img src="@/assets/svg/linkedin.svg" alt="linkedin">
      </network>
      <network network="twitter">
          <img src="@/assets/svg/gorjeo.svg" alt="Twitter">
      </network>
      <network network="googleplus">
        <img src="@/assets/svg/google-plus.svg" alt="Google +">
      </network>
    </div>
  </social-sharing>
  </div>
</template>

<script>
export default {
  props: {
    url: String,
    titulo: String
    }
  }
</script>

<style lang="scss" scoped>
.social-list {
  height: auto;
  width: 100%;
  display: flex;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-column-gap: 15px;
  margin: 15px 0;
}
img {
  transition: 0.5s;
  width: 100%;
  cursor: pointer;
  &:hover {
    background-color: #65A3AE;
  }
}
</style>
