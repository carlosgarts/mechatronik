<template>
  <div class="prod-widget">
    <ul v-if="productos != []">
      <li v-for="producto in productos">
        <nuxt-link class="prod-card" :to="'/productos/'+ producto.slug">
          <div class="card-content">
            <img :src="producto.images[0].src" alt="product image">
            <h3>{{producto.name}}</h3>
            <h4>{{producto.acf.modelo}}</h4>
            <div  class="card-description" v-html="producto.short_description"></div>
          </div>
        </nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    categoria: String,
    cantidad: {
      type: String,
      default: '3'
    }
  },
  data() {
    return {
      productos: []
    }
  },
  mounted: async function() {
      var consulta = ''
      try {
        var Product = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&per_page='+ this.cantidad +'&category=' + this.categoria);
        this.productos = Product.data;
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
    width: 100%;
    display: grid;
    grid-template-columns: 1fr;
    grid-column-gap: 25px;
    @media (min-width: 600px) {
      grid-template-columns: 1fr 1fr;
    }
    @media (min-width: 900px) {
      grid-template-columns: 1fr 1fr 1fr;
    }
    @media (min-width: 1200px) {
      grid-template-columns: 1fr 1fr 1fr 1fr;
    }
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
  img {
    width: 100%;
    height: 200px;
    object-fit: contain;
  }

  .prod-card {
    position: relative;
    width: 100%;
    height: 100%;
    text-decoration: none;
    .card-content {
      transition: transform .5s;
      position: relative;
      width: 100%;
      height: 100%;
      padding: 25px;
      background-color: white;
      border: 1px solid #CCCCCC;
      color: black;
      h3 {
        text-align: left;
        color: #65A3AE;
      }
      h4 {
        text-align: left;
        margin: 10px 0;
        font-weight: 500;
        font-size: 14px;
        line-height: 1.3;
        color: #87888a;
      }
      img {
        width: 100%;
        height: 200px;
        object-fit: contain;
      }
      p {
        word-break: break-all;
        height: 55px;
        overflow:hidden;
        margin-top: 10px;
        margin-bottom: 30px;
        -webkit-mask-image: -webkit-gradient(linear, left top, left bottom, from(rgba(0,0,0,1)), to(rgba(0,0,0,0)));
        mask-image: gradient(linear, left top, left bottom, from(rgba(0,0,0,1)), to(rgba(0,0,0,0)));
      }
      .card-description {
        display: none;
        word-break: break-all;
        font-size: 12px;
        line-height: 2;
        p {
          ul {
            padding: 0;
          }
        }
      }
    }
  }
</style>
