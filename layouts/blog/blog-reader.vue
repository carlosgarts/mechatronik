<template>
  <div id="post-reader">
    <loading v-if="isLoading == true"/>
    <div class="post" v-for="post in posts" v-else>
      <div class="titulo" v-bind:style="{ backgroundImage: 'url(' + post.featured_image_url + ')' }">
        <h2>{{ post.title.rendered }}</h2>
      </div>
      <div class="content" v-html="post.content.rendered"></div>
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
    margin-top: 150px;
    height: 60vh;
    background-repeat: no-repeat;
    background-size: cover;
    margin-top: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    @media (min-width: 1000px) {
      margin-top: 140px;
    }
    h2 {
      color: white;
      text-align: center;
      font-size: calc(32px + (55 - 32) * ((100vw - 300px) / (1600 - 300)));
      max-width: 80%;
    }
  }

  .content {
    width: 60%;
    margin: 150px;
    margin-top: 0px;
    padding: 80px;
    padding-top: 20px;
  }

  .service-content {
    width: 100%;
    min-height: 60vh;
    display: grid;
    grid-template-columns: 1fr;
    z-index: 5;
    position: relative;
    margin-top: 50px;
    margin-bottom: 100px;
    @media (min-width: 700px) {
      grid-template-columns: 1fr 1fr;
    }
    .text {
      text-align: right;
      padding-left: 7.5%;
      padding-right: 7.5%;
      display: flex;
      flex-flow: column;
      justify-content: center;
      align-items: flex-end;
      .tbb {
        margin-left: 0;
        margin-right: 0;
        border-color: black;
        h2 {
          transition: 0.5s;
          color: black;
          border-color: black;
          @media (max-width: 400px) {
            font-size: 30px;
          }
        }
      }
      p {
        line-height: 1.5;
      }
    }
    .image {
      height: 300px;
      width: 85%;
      overflow: hidden;
      margin: auto;
      margin-top: 20px;
      @media (min-width: 700px) {
        height: 85%;
        width: 85%;
        margin: auto auto;
      }
      img {
        transition: transform 10s ease;
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
      img:hover {
        transform: scale(1.3);
      }
    }
  }
  .service-content:nth-child(2n) {
    .text {
      text-align: left;
      align-items: flex-start;
      @media (min-width: 700px) {
        grid-column: 2 / 3;
      }
    }
    .image {
      @media (min-width: 700px) {
        grid-column: 1 / 2;
        grid-row: 1;
      }
    }
  }

</style>
