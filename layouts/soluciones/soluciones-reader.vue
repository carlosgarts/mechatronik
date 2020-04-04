<template>
  <div id="post-reader">
    <loading v-if="isLoading == true"/>
    <div class="post" v-for="post in posts" v-else>
      <!-- <div class="titulo" v-bind:style="{ backgroundImage: 'url(' + post.featured_image_url + ')' }">
        <h2>{{ post.title.rendered }}</h2>
      </div> -->
      <div class="content" >
        <p class="nav-history"><a href="https://mechatronik-group.com/">Inicio</a> &#10095 <a href="https://mechatronik-group.com/soluciones">Soluciones</a> &#10095 {{post.title.rendered}}</p>
        <h1 class="service-title">{{post.title.rendered}}</h1>
        <div class="format" v-html="post.content.rendered"></div>
        <solser modo="servicios2" />
      </div>
    </div>
  </div>
</template>

<script>
import loading from '../partials/loading.vue'
import axios from 'axios'
import solser from '../partials/widgets/soluciones-servicios.vue'

export default {
  components: {
    loading,
    solser
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
        consulta = 'https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=19&slug=';
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
    width: 90%;
    margin-left: 5%;
    margin-right: 5%;
    margin-top: 0px;
    margin-bottom: 0px;
    padding: 0;
    padding-top: 20px;
    //overflow: hidden;
    @media (min-width: 800px) {
      padding: 80px
    }
      .nav-history {
        margin: 0;
        //margin-top: 25px;
      }
    }

    .service-title {
      transition: 0.5s;
      text-align: left;
      margin: 30px 0;
      color: #2d373c;
      font-size: 1.8rem;
      @media (min-width: 800px) {
        font-size: 3rem;
      }
    }
</style>
