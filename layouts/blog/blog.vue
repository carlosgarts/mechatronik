<template>
    <div id="blog-list">
      <img class="parallax-background" v-rellax="{speed: -10, vertical: true, horizontal: false}" src="../../assets/images/Soluciones/bg-clear.png" alt="">
      <loading v-if="isLoading == true"/>
      <div class="post-grid" v-else>
        <div class="posts" v-scroll-reveal.reset v-for="post in posts" :key="post.id">
          <nuxt-link :to="{ name: 'blog-slug', params: { slug: post.slug, id: post.id} }">
          <div class="image">
            <div class="foreground"></div>
            <img :src="post.featured_image_url">
          </div>
          <div class="text">
            <div class="title">
            <h2><strong>{{post.title.rendered}}</strong></h2>
            </div>
            <div class="excerpt" v-html="post.excerpt.rendered"></div>
          </div>
          </nuxt-link>
        </div>
      </div>
    </div>

</template>

<script>
import loading from '../partials/loading.vue'

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
        var Blogis = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=17');
        this.posts = Blogis.data;
        this.isLoading = false;
      } catch (e) {
        console.log(e);
      }
  }
  // fetch({ store }) {
  //   return this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts').then((res) => {
  //     store.commit('frontPagePosts', res.data)
  //   }).catch((error) => {
  //     console.log(error)
  //   })
  // },
  //
  // computed: {
  //   posts() {
  //     return this.$store.state.posts
  //   }
  // }
}
</script>

<style lang="scss" scoped>
  #blog-list {
    height: auto;
    width: 90vw;
    align-self: flex-end;
    position: relative;
    @media (min-width: 800px) {
      width: 80vw;
    }
    .parallax-background {
      width: 100%;
      position: absolute;
      z-index: 1;
    }
  }

  .post-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    z-index: 5;
    position: relative;
    grid-column-gap: 15px;
    grid-row-gap: 15px;
    @media (min-width: 800px) {

    }
  }

  .posts {
    grid-column: span 2;
    width: 100%;
    background-color: #ebf0f5;
    a {
      text-decoration: none;
      color: black;
      display: grid;
      grid-template-columns: 1fr;
      @media (min-width: 930px) {
        grid-template-columns: 1fr;
      }
    }
    .image {
      width: 100%;
      height: 200px;
      position: relative;
      overflow: hidden;
      &:hover {
        img {
            transform: scale(110%, 110%);
        }
      }
      .foreground {
        display:block;
        position: absolute;
        width: 100%;
        height: 100%;
        background-color: rgba(#000, 0.5);
        left: 0;
        top: 0;
        z-index: 15;
      }
      img {
        transition: transform 1s ease;
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    .text {
      margin: 25px;
      margin-bottom: 9px;
      z-index: 20;
    }
  }
  .posts:nth-child(1) {
    display: block;
    grid-column: 1 / 5;
    grid-row: 1 / 3;
    position: relative;
    @media (min-width: 930px) {
      grid-column: 1 / 3;
    }
    a {
      display: inline;
    }
    .text {
      position: absolute;
      bottom: 0;
      text-align: justify;
      color: white;
      line-height: 1.4;
      .title {
        color: #65A3AE;
      }
      .excerpt {
        p {
          margin-bottom: 0px;
        }
      }
    }
    .image {
      height: 100%;
      width: 100%;
    }
  }
  .posts:nth-child(2), .posts:nth-child(3), .posts:nth-child(4), .posts:nth-child(5){
    display: block;
    grid-column: span 2;
    @media (min-width: 930px) {
      grid-column: span 1
    }
    a {
      display: inline;
    }
    .text {
      position: absolute;
      bottom: 0;
      color: white;
      .title {
        font-size: 12px;
      }
      .excerpt {
        display: none;
      }
    }
    .image {
      height: 100%;
      width: 100%;
    }
  }

</style>
