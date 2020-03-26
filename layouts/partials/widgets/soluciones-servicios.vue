<template>
  <div class="sol-ser">
    <div class="soluciones" v-if="modo == 'soluciones'">
      <ul>
        <li v-for="post in posts">
          <nuxt-link :to="'/soluciones/'+ post.slug">{{post.title.rendered}}</nuxt-link>
        </li>
      </ul>
    </div>
    <div class="servicios" v-if="modo == 'servicios'">
      <ul class="item-list">
        <li v-for="post in posts">
          <nuxt-link :to="'/servicios/'+ post.slug"> {{post.title.rendered}} </nuxt-link>
        </li>
      </ul>
    </div>
    <div class="servicios" v-if="modo == 'servicios2'">
      <ul class="servicios2">
        <li v-for="post in posts">
          <nuxt-link :to="'/servicios/'+ post.slug"> <img :src="post.featured_image_url" alt="Servicio"> <p>{{post.title.rendered}}</p> </nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    modo: String
  },
  data() {
    return {
      posts: []
    }
  },
  mounted: async function() {
    if (this.modo == "servicios" || this.modo == "servicios2") {
      try {
        var Servs = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=18');
        this.posts = Servs.data;
      } catch (e) {
        console.log(e);
      }
    }
    if (this.modo == "soluciones") {
      try {
        var Servs = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=19');
        this.posts = Servs.data;
      } catch (e) {
        console.log(e);
      }
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
