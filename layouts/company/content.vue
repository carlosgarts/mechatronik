<template>
  <div>
    <loading v-if="isLoading == true"/>
    <div class="post" v-for="post in posts" v-else>
      <div class="format" v-html="post.content.rendered"></div>
    </div>
  </div>
</template>

<script>
import loading from '../partials/loading.vue'
import axios from 'axios'

export default {
  components: {
    loading
  },
  data() {
    return {
      posts: [],
      isLoading: true
    }
  },
  mounted: async function() {
      try {
        var Post = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/pages?slug=compania');
        this.posts = Post.data;
        this.isLoading = false;
      } catch (e) {
        this.isLoading = false;
        console.log(e);
      }
  }
}
</script>

<style lang="scss">

.valores {
  margin-left: 5%;
  margin-right: 5%;
  width: 90%;
  display: grid;
  grid-template-columns: 1fr;
  @media (min-width: 600px) {
    grid-template-columns: 1fr 1fr;
  }
  .wp-block-column {
    padding: 2.5% 3%;
    h2 {
      font-family: Raleway;
      font-style: normal;
      font-weight: bold;
      font-size: calc(30px + (70 - 30) * ((100vw - 300px) / (1600 - 300)));
      color: black;
      margin-top: 10px;
    }
    p {
      font-family: Raleway;
      font-style: normal;
      font-weight: normal;
      font-size: calc(16px + (20 - 16) * ((100vw - 300px) / (1600 - 300)));
      line-height: 1.4;
      text-align: center;
      color: black;
    }
  }
  .mision {
    border-bottom: 2px solid black;
    @media (min-width: 600px) {
      border-bottom: 0;
      border-right: 2px solid black;
    }
  }
}

</style>
