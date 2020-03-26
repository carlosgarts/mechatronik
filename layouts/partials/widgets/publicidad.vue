<template>
  <div class="publicidad">
    <ul v-if="destacados != []">
      <li v-for="destacado in destacados">
        <nuxt-link :to="'/productos/'+ destacado.slug">
          <img :src="destacado.images[0].src" alt="">
          <h4>{{destacado.name}}</h4>
        </nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      destacados: []
    }
  },
  mounted: async function() {
      try {
        var Product = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&featured=true&per_page=3');
        this.destacados = Product.data;
      } catch (e) {
        console.log(e);
      }
  }
}
</script>

<style lang="scss" scoped>
  ul {
    list-style: none;
    padding: 0;
    li {
      margin-top: 15px;
      margin-bottom: 15px;
    }
  }
  a {
    text-decoration: none;
    color: white;
    position: relative;
  }
  h4  {
    position: absolute;
    bottom: 0;
    width: 100%;
    color: white;
    text-align: left;
    padding: 5px;
    padding-left: 10px;
    background: rgb(101,163,174);
    background: linear-gradient(90deg, rgba(101,163,174,0.9080766095500701) 37%, rgba(255,255,255,0) 100%);
  }
  img {
    width: 100%;
  }
</style>
