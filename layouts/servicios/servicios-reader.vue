<template>
  <div id="post-reader">
    <loading v-if="isLoading == true"/>
    <div class="post" v-for="post in posts" v-else>
      <div class="titulo" v-bind:style="{ backgroundImage: 'url(' + post.featured_image_url + ')' }">
        <h2>{{ post.title.rendered }}</h2>
      </div>
      <div class="content" >
        <div class="format" v-html="post.content.rendered"></div>
      </div>
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
        const slug = this.$route.params.slug;
        var consulta;
        consulta = 'https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=18&slug=';
        consulta = consulta.concat(slug);
        console.log(consulta);
        var Post = await this.$axios.get(consulta);
        this.posts = Post.data;
        this.isLoading = false;
      } catch (e) {
        this.isLoading = false;
        console.log(e);
      }
  }
  // async asyncData({params}) {
  //   return axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?slug=' + params.slug).ten((res) => {
  //     return {
  //       post: res.data
  //     }
  //   })
  // }
  // mounted: async function() {
  //     try {
  //       var Post = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?slug=' + params.slug);
  //       this.post = Post.data;
  //       this.isLoading = false;
  //     } catch (e) {
  //       this.isLoading = false;
  //       console.log(e);
  //     }
  // }
}
</script>

<style lang="scss" scoped>
  #post-reader {
    height: auto;
    width: 100vw;
    min-height: 100vh;
    align-self: flex-end;
    position: relative;
    .parallax-background {
      width: 100%;
      position: absolute;
      z-index: 1;
    }
  }

  .titulo {
    height: 40vh;
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
    @media (min-width: 1000px) {

    }
    h2 {
      color: white;
      text-align: center;
      text-shadow: 5px 5px 1px gray;
      font-size: calc(32px + (55 - 32) * ((100vw - 300px) / (1600 - 300)));
      max-width: 80%;
    }
  }

  .content {
    width: 65%;
    margin-left: 17.5%;
    margin-right: 17.5%;
    margin-top: 0px;
    margin-bottom: 0px;
    padding: 80px;
    padding-top: 20px;
    overflow: hidden;
    }
</style>
