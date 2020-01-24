<template>
  <div class="section">
    <div id="product-widget">
      <h3>Productos</h3>
      <p class="text">
        Our goal is to provide innovative and future-proof solutions for our
        customers. Our products are the foundation. Visions become concrete ideas,
        giving rise to products that create mechatronic drive solutions.
      </p>
      <div class="product-selector">
        <select v-model="selectedCategory" @change="selectCategory">
          <option v-for="category, i in categories" :key="category.id" :value="i++">{{category.name}}</option>
        </select>
      </div>
        <div class="product-displayer" v-if="categories[selectedCategory] != null" :key="selectedCategory">
          <div class="category-text">
            <h4>{{categories[selectedCategory].name}}</h4>
            <p>{{categories[selectedCategory].description}}</p>
            <nuxt-link :to="'/categorias/'+ categories[selectedCategory].slug">Ver mas productos  &#10095</nuxt-link>
          </div>
          <div class="category-cover" v-if="categories[selectedCategory].image != null">
            <img :src="categories[selectedCategory].image.src">
          </div>
        </div>
        <div class="" v-else>
          Cargando
        </div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      selectedCategory: '1',
      categories: []
    }
  },
  methods: {
    selectCategory: function () {
      // this.selectedCategory = '';
    }
  },
  mounted: async function() {
      try {
        var Categories = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products/categories?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f');
        this.categories = Categories.data;
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

  .product-selector {
    display: block;
    width: 100%;
    select {
      padding: 9px 9px;
      option {

      }
    }
  }

  #product-widget {
    display: block;
    margin: 0;
    text-align: left;
    h3 {
      color: black;
      text-align: left;
      letter-spacing: 0px;
      font-style: normal;
      font-weight: normal;
      font-size: calc(35px + (50 - 35) * ((100vw - 300px) / (1600 - 300)));
    }
  }

  .text {
      color: #3e3d40;
      line-height: 1.37;
      max-width: 720px;
  }

  .category-text {
    height: 100%;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    flex-flow: column;
    align-items: flex-start;
    justify-content: center;
    h4 {
      font-size: calc(20px + (40 - 20) * ((100vw - 300px) / (1600 - 300)));
      color: #65A3AE;
      font-weight: normal;
      letter-spacing: -1px;
      margin-bottom: 10px;
      margin-top: 10px;
    }
    p {
      color: #87888a;
      line-height: 1.5;
      text-align: justify;
    }
    a {
      transition: 0.5s;
      color:#65A3AE;
      text-decoration: none;
      border: 1px solid #65A3AE;
      padding: 9px 14px;
      margin-bottom: 16px;
    }
    a:hover {
      color:#FFFFFF;
      background-color: #65A3AE;
      text-decoration: none;
      border: 1px solid #65A3AE;
      padding: 9px 14px;
      margin-bottom: 16px;
    }
  }

  .product-displayer {
    display: grid;
    width: 100%;
    grid-template-columns: 1fr;
    grid-column-gap: 25px;
    border-top: 1px solid #CCCCCC;
    border-bottom: 1px solid #CCCCCC;
    margin-top: 25px;
    @media (min-width: 800px) {
      grid-template-columns: 1fr 1fr;
    }
    .category-cover {
      position: relative;
      width: 100%;
      max-height: 400px;
      grid-row: 1 / 2;
      img {
        width: 100%;
        height: 100%;
        position: static;
        object-fit: contain;
        @media (min-width: 800px) {
          //height: auto;
          position: relative;
          //top: 20px;
          object-fit: cover;
        }
      }
    }
  }

</style>
