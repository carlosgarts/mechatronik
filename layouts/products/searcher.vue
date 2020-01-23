<template>
  <div>
    <loading v-if="productos == undefined"/>
    <div class="product--searcher" v-else>
      <div class="product--header">
        <div class="header--content">
          <h2>Productos Mechatronik</h2>
          <p>
            From the fast delivery to extensive application and technical support,
            our quality products include more added value than any others on the market.
          </p>
          <!-- <select v-model="selectedCategory" @change="selectCategory" v-if="Modo == 2">
            <option v-for="category, i in categories" :key="category.id" :value="i++">{{category.name}}</option>
          </select> -->
          <input  class="searcher" v-model="searcher" type="text" @keyup.enter="search(searcher)" name="search" placeholder="Search here" value="">
          <button class="searcher--btn" type="button" name="button" @click="search(searcher)">Buscar</button>
        </div>
      </div>
      <img class="big-arrow" src="../../assets/svg/great-arrow.svg" alt="arrow down">
      <div class="product--list">
        <div class="list--content">
          <h2>Productos</h2>
          <div class="select-box">
              <div class="lister">
                <nuxt-link :to="'/productos/'+ producto.slug" class="prod-card" v-for="producto in paginatedData" :key="pageNumber" >
                  <img :src="producto.images[0].src" alt="product image">
                  <h3>{{producto.name}}</h3>
                  <h4>{{producto.acf.modelo}}</h4>
                  <div  class="card-description" v-html="producto.short_description"></div>
                </nuxt-link>
              </div>
              <div class="changers">
                <a class="prev" @click="prevPage()" v-bind:class="{ unactive: (pageNumber === 0) }">&#10094;</a>
                <a class="next" @click="nextPage()" v-bind:class="{ unactive: (pageNumber >= pageCount -1)}">&#10095;</a>
              </div>
          </div>
        </div>
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
  props: {
    Modo: {
      type: Number,
      default: 1 // 1 : Todos | 2 : Categoria | 3 : Busqueda
    },
    categoriaId: {
      type: Number
    },
    tagId: {
      type: Number
    },
    perPage: Number,
    idQuery: Number,
    size: {
      type : Number,
      required : false,
      default : 8
    }
  },
  data: function() {
    return {
      productos: [],
      pageNumber: 0,
      refresher: 0,
      selectedCategory: '1',
      categories: [],
      searcher: ''
    }
  },
  methods : {
    nextPage() {
      this.pageNumber++;
    },
    prevPage() {
      this.pageNumber--;
    },
    dPage(number) {
      this.pageNumber = number;
    },
    search: async function (search) {
      try {
        this.isLoading = true;
        let consulta = 'https://blog.mechatronik-group.com/wp-json/wc/v3/products?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&per_page=50&search=';
        consulta = consulta.concat(search);
        var Productos = await this.$axios.get(consulta);
        this.productos = Productos.data;
        this.isLoading = false;
      } catch (e) {
        console.log(e);
        this.isLoading = false;
      }
    }
  },
  computed : {
    pageCount(){
      let l = this.productos.length,
          s = this.size;
      return Math.ceil(l/s);
    },
    paginatedData(){
      const start = this.pageNumber * this.size,
            end = start + this.size;
       return this.productos.slice(start, end);
    }
  },
  watch: {
    idQuery() {
      this.pageNumber = 0;
    }
  },
  mounted: async function() {
      //Modo General
      if (this.Modo == 1) {
        try {
          var Productos = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&per_page=50');
          this.productos = Productos.data;
          this.isLoading = false;
        } catch (e) {
          console.log(e);
          this.isLoading = false;
        }
      }//Segun Categoria
      if (this.Modo == 2) {
        console.log('entro en categorias');
        try {
          var Productos = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&per_page=50&category=' + this.categoriaId);
          this.productos = Productos.data;
          this.isLoading = false;
        } catch (e) {
          console.log(e);
        }
      }//Segun Etiqueta
      if (this.Modo == 3) {
        console.log('entro en marcas');
        try {
          var Productos = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&per_page=50&tag=' + this.tagId);
          this.productos = Productos.data;
          this.isLoading = false;
        } catch (e) {
          console.log(e);
        }
      }
  },
  // beforeUpdate:  async function (){
  //   if (this.refresher < 3) {
  //     try {
  //       const id = this.idQuery;
  //       var consulta;
  //       if (this.Modo == 'si') {
  //         consulta = 'https://system.mechatronik-group.com/api/pormarca/';
  //       }
  //       else {
  //         consulta = 'https://system.mechatronik-group.com/api/porcategoria/';
  //       }
  //       consulta = consulta.concat(id);
  //       var Productos = await this.$axios.get(consulta);
  //       this.productos = Productos.data.productos;
  //       this.isLoading = false;
  //     } catch (e) {
  //       this.isLoading = false;
  //       console.log(e);
  //     }
  //     this.refresher++;
  //   }
  // }
}
</script>

<style lang="scss" scoped>

.product--searcher {
  width: 100vw;
  h2 {
    margin: 0;
    font-size: calc(35px + (50 - 35) * ((100vw - 300px) / (1600 - 300)));
    font-style: normal;
    font-weight: normal;
  }
  h3 {
    font-size: 25px;
    font-style: normal;
    font-weight: normal;
    word-break: break-all;
    overflow: hidden;
  }
}
.product--header {
  display:flex;
  justify-content: center;
  width: 100%;
  background-color: #F3F3F3;
  position: relative;
  z-index: 2;
  .header--content {
    width: 90%;
    margin: 45px 0;
    max-width: 1200px;
    @media (min-width: 900px) {
      width: 80%;
    }
    p {
      max-width: 800px;
      line-height: 1.4;
      margin: 30px 0;
    }
  }
}
.big-arrow {
  width: 100%;
  margin: 0;
  position: relative;
  top: -1px;
  z-index: 1;
}
.product--list {
  display: flex;
  width: 100%;
  justify-content: center;
  .list--content {
    display: grid;
    width: 90%;
    max-width: 1200px;
    position: relative;
    margin-bottom: 10%;
    @media (min-width: 900px) {
      width: 80%;
    }
  }
}

.lister {
  display: grid;
  grid-template-columns: 1fr;
  width: 100%;
  grid-column-gap: 15px;
  grid-row-gap: 15px;
  min-height: 300px;
  margin: 30px 0;
  @media (min-width: 600px) {
    grid-template-columns: 1fr 1fr;
  }
  @media (min-width: 900px) {
    grid-template-columns: 1fr 1fr 1fr;
  }
  @media (min-width: 1320px) {
    grid-template-columns: 1fr 1fr 1fr 1fr;
  }
}

.prod-card {
  width: 280px;
  padding: 25px;
  background-color: white;
  border: 1px solid #CCCCCC;
  text-decoration: none;
  color: black;
  h3 {
    text-align: left;
    color: #65A3AE;
  }
  h4 {
    text-align: left;
    margin: 10px 0;
    font-weight: 500;
    font-size: 18px;
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
  }
}

.buttom-link {
  transition: 0.5s;
  text-decoration: none;
  color: white;
  background-color: white;
  color: #65A3AE;
  padding: 7px 15px;
  display: block;
  width: 143px;
  border-radius: 18px;
  -webkit-box-shadow: 2px 6px 8px 1px rgba(140,140,140,0.4);
  -moz-box-shadow: 2px 6px 8px 1px rgba(140,140,140,0.4);
  box-shadow: 2px 6px 8px 1px rgba(140,140,140,0.4);
  &:hover {
    background-color: #65A3AE;
    color: white;
  }
}

.changers{
  padding: 20px;
  font-size: 50px;
  text-align: center;
  a {
    cursor: pointer;
    :hover {
      color: #65A3AE;
    }
    :disabled {
      color: gray;
    }
  }
  .unactive {
    display: none;
  }
}

.searcher {
  background-color: #F3F3F3;
  //border: 1px solid #CCCCCC;
  border: none;
  border-bottom: 2px solid #65A3AE;
  padding: 9px;
}

.searcher--btn {
  transition: 0.5s;
  color: #65A3AE;
  background-color: white;
  border: 1px solid #CCCCCC;
  padding: 9px;
  cursor: pointer;
}
.searcher--btn:hover {
  color: white;
  background-color: #65A3AE;
  border: 1px solid #CCCCCC;
  padding: 9px;
}

</style>
