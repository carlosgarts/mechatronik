<template>
  <div class="recientes">
    <ul>

      <li v-for="post in posts">
        <nuxt-link :to="'/blog/'+ post.slug">{{post.title.rendered}}</nuxt-link>
      </li>

    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: []
    }
  },
  mounted: async function() {
      try {
        var Blogis = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=17&per_page=5');
        this.posts = Blogis.data;
      } catch (e) {
        console.log(e);
      }
  }
}
</script>

<style lang="scss" scoped>
</style>
