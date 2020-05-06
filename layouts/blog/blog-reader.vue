<template>
  <div id="post-reader">
    <loading v-if="isLoading == true"/>
    <content class="post" v-for="post in posts" v-else>
      <div class="titulo" v-bind:style="{ backgroundImage: 'url(' + post.featured_image_url + ')' }">
        <h2>{{ post.title.rendered }}</h2>
      </div>
      <div class="content" >
        <div class="format" v-html="post.content.rendered"></div>
        <div class="side">
          <sidebar v-if="isLoading == false" :titular="post.title.rendered"/>
        </div>
      </div>
    </content>
  </div>
</template>

<script>
import loading from '../partials/loading.vue'
import axios from 'axios'
import sidebar from '../partials/sidebar.vue'
import blogpost from '../../assets/text/posts.json'

// var foundData = blogpost.filter(d => d.slug === this.$route.params.slug);
// console.log(foundData);

export default {
  components: {
    loading,
    sidebar
  },
  data() {
    return {
      posts: blogpost.filter(d => d.slug === this.$route.params.slug),
      isLoading: false
    }
  },
  mounted: async function() {
      try {
        const slug = this.$route.params.slug;
        var consulta;
        this.isLoading = true;
        consulta = 'https://blog.mechatronik-group.com/wp-json/wp/v2/posts?slug=';
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
    height: 60vh;
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
    @media (min-width: 1000px) {
    }
    h2 {
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      text-align: center;
      font-size: calc(32px + (55 - 32) * ((100vw - 300px) / (1600 - 300)));
      width: 100%;
      height: 100%;
      padding-left: 10%;
      padding-right: 10%;
      background-color: rgba(black, 0.5);
    }
  }

  .content {
    display: grid;
    grid-template-columns: 100%;
    grid-column-gap: 70px;
    width: 90%;
    margin-left: 5%;
    margin-right: 5%;
    margin-top: 0px;
    margin-bottom: 0px;
    padding: 0;
    padding-top: 20px;
    overflow: hidden;
    @media (min-width: 800px) {
      grid-template-columns: calc(70% - 70px)  30%;
      width: 80%;
      margin-left: 10%;
      margin-right: 10%;
      padding: 80px;
    }
    }
</style>
