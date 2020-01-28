<template>
  <div class="section">
    <div id="blog-widget">
      <h3>Blog & Novedades</h3>
      <div class="magazin">
        <div class="squares" v-for="post in posts">
          <nuxt-link :to="'/blog/'+ post.slug">
            <div class="cover">
              <img :src="post.featured_image_url" alt="">
            </div>
            <div class="text">
              <h4>{{post.title.rendered}}</h4>
              <p v-html="post.excerpt.rendered"></p>
            </div>
            <div class="right">
              &#10095
            </div>
          </nuxt-link>
        </div>
      </div>
    </div>
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
        var Blogis = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?per_page=4&categories=17');
        this.posts = Blogis.data;
      } catch (e) {
        console.log(e);
      }
  }
}
</script>

<style lang="scss" scoped>

  .section {
    display: block;
  }

  .magazin {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-column-gap: 15px;
    grid-row-gap: 15px;
    height: 100%;
    @media (min-width: 800px) {
      grid-template-rows: 1fr 1fr;
      grid-template-rows: 50% 50%;
    }
  }

  .squares {
    text-align: left;
    border: 1px solid #CCCCCC;
    position: relative;
    a {
      text-decoration: none;
      color: black;
    }

    .cover {
      img {
        transition: transform 3s ease;
        object-fit: cover;
      }
      img:hover {
        transform: scale(1.3);
      }
    }

    .text {
      margin: 25px;
      max-height: 170px;
      overflow: hidden;
      line-height: 1.3;
      h4 {
        margin: 0;
        font-size: 16px;
        @media (min-width: 800px) {
          font-size: 21px;
        }
      }
      p {
        font-size: 13px;
        @media (min-width: 800px) {
          font-size: 21px;
        }
      }
    }

    .right {
      position: absolute;
      right: 0;
      margin: 25px;
      display: block;
      height: auto;
      width: 31px;
      text-align: center;
      font-size: 25px;
      color: #65A3AE;
      border: 2px solid #65A3AE;
      border-radius: 50%;
    }
  }

  .squares:nth-child(1) {
    width: 100%;
    grid-column: 1 / 5;
    grid-row: 1 / 2;
    @media (min-width: 800px) {
      grid-column: 1 / 3;
      grid-row: 1 / 3;
    }
    .cover {
      width: 100%;
      overflow: hidden;
      height: auto;
      max-height: 450px;
      img {
        width: 100%;
        object-fit: cover;
      }
    }
    .text {
      max-height: 125px;
      -webkit-mask-image: -webkit-gradient(linear, left top, left bottom, from(black), to(rgba(0, 0, 0, 0)));
      mask-image: gradient(linear, left top, left bottom, from(black), to(rgba(0, 0, 0, 0)));
      h4 {
        color: #65A3AE;
      }
    }
    .right {
      bottom: 0;
    }
  }

  .squares:nth-child(2) {
    transition: 0.5s;
    width: 100%;
    max-height: 280px;
    background-color: #65A3AE;
    color: white;
    @media (min-width: 400px) {
      max-height: 100%;
    }
    @media (max-width: 800px) {
      grid-column: 1 / 3;
    }
    a {
      text-decoration: none;
      color: white;
    }
    .cover {
      display: none;
    }
    .text {
      -webkit-mask-image: -webkit-gradient(linear, left top, left bottom, from(black), to(rgba(0, 0, 0, 0)));
      mask-image: gradient(linear, left top, left bottom, from(black), to(rgba(0, 0, 0, 0)));
    }
    .right {
      color: white;
      border: 2px solid white;
      bottom: 0;
    }
  }

  .squares:nth-child(2):hover {
    background-color: #58818B;
  }

  .squares:nth-child(3) {
    width: 100%;
    max-height: 280px;
    @media (min-width: 400px) {
      max-height: 100%;
    }
    @media (max-width: 800px) {
      grid-column: 3 / 5;
    }
    .cover {
      display: none;
    }
    .text {
      color: #65A3AE;
      -webkit-mask-image: -webkit-gradient(linear, left top, left bottom, from(black), to(rgba(0, 0, 0, 0)));
      mask-image: gradient(linear, left top, left bottom, from(black), to(rgba(0, 0, 0, 0)));
    }
    .right {
      bottom: 0;
    }
  }

  .squares:nth-child(4) {
    width: 100%;
    max-height: 250px;
    grid-column: 1 / 5;
    @media (min-width: 800px) {
      grid-column: 3 / 5;
      max-height: 330px;
    }
    .cover {
      width: 100%;
      height: 100%;
      max-height: 280px;
      overflow: hidden;
      img {
        width: 100%;
        height: 100%;
        max-height: 100%;
        object-fit: cover;
      }
    }
    .text {
      position: absolute;
      bottom: 0;
      color: white;
      p {
        display: none;
      }
    }
    .right {
      top: 0;
      color: white;
      border: 2px solid white;
    }
  }

  #blog-widget {
    display: block;
    margin: 25px 0;
    @media (min-width: 800px) {
      margin: 50px 0;
    }
    @media (min-width: 1100px) {

    }
    h3 {
      color: black;
      text-align: left;
      letter-spacing: 0px;
      font-style: normal;
      font-weight: normal;
      font-size: calc(35px + (50 - 35) * ((100vw - 300px) / (1600 - 300)));
      margin-bottom: 30px;
    }
  }

</style>
