<template>
  <div>
    <loading v-if="productos == undefined"/>
    <div class="section" id="product--lister" v-else>
      <div class="product--list">
        <h2>Productos</h2>
        <div class="select-box">
            <div class="lister">
              <div class="prod-card" v-for="producto in paginatedData" :key="pageNumber" >
                <img :src="producto.fotos.substr(0, producto.fotos.lastIndexOf(';'))" alt="product image">
                <h3>{{producto.nombre}}</h3>
                <p>{{producto.descripcion}}</p>
                <nuxt-link :to="'/productos/'+ producto.id" class="buttom-link">Ver Producto &#10095;</nuxt-link>
              </div>
            </div>
            <div class="side-tag"> <span>&#9472&#9472&#9472</span>Productos <span class="smallArrow">&#10095;</span> {{Marca}}</div>
            <div class="changers">
              <a class="prev" @click="prevPage()" v-bind:class="{ unactive: (pageNumber === 0) }">&#10094;</a>
              <a class="next" @click="nextPage()" v-bind:class="{ unactive: (pageNumber >= pageCount -1)}">&#10095;</a>
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
    porMarca: String,
    Marca: String,
    Categoria: String,
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
      refresher: 0
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
      try {
        const id = this.idQuery;
        var consulta;
        if (this.porMarca == true) {
          consulta = 'http://mechatronik-group.com:4000/api/pormarca/';
        }
        else {
          consulta = 'http://mechatronik-group.com:4000/api/porcategoria/';
        }
        consulta = consulta.concat(id);
        var Productos = await this.$axios.get(consulta);
        this.productos = Productos.data.productos;
        this.isLoading = false;
      } catch (e) {
        this.isLoading = false;
        console.log(e);
      }
  },
  beforeUpdate:  async function (){
    if (this.refresher < 3) {
      try {
        const id = this.idQuery;
        var consulta;
        if (this.porMarca == 'si') {
          consulta = 'http://mechatronik-group.com:4000/api/pormarca/';
        }
        else {
          consulta = 'http://mechatronik-group.com:4000/api/porcategoria/';
        }
        consulta = consulta.concat(id);
        var Productos = await this.$axios.get(consulta);
        this.productos = Productos.data.productos;
        this.isLoading = false;
      } catch (e) {
        this.isLoading = false;
        console.log(e);
      }
      this.refresher++;
    }
  }
}
</script>

<style lang="scss" scoped>

h2 {
  font-size: 50px;
  font-family: Raleway;
  font-style: normal;
  font-weight: bold;
  margin-left: 5%;
}

h3 {
  font-size: 25px;
  font-family: Raleway;
  font-style: normal;
  font-weight: bold;
  word-break: break-all;
  height: 58px;
  overflow: hidden;
}

p {
  word-break: break-all;
  height: 55px;
  overflow:hidden;
  -webkit-mask-image: -webkit-gradient(linear, left top, left bottom, from(rgba(0,0,0,1)), to(rgba(0,0,0,0)));
  mask-image: gradient(linear, left top, left bottom, from(rgba(0,0,0,1)), to(rgba(0,0,0,0)));
}

.section {
  align-items: flex-start;
  text-align: left;
  background-color: white;
}

.product--list {
  width: 80%;
  position: relative;
  margin-bottom: 10%;
}

.lister {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  min-height: 300px;
}

.prod-card {
  width: 270px;
  padding: 25px;
  background-color: white;
  margin: 16px;
  -webkit-box-shadow: 6px 6px 17px 2px rgba(140,140,140,1);
  -moz-box-shadow: 6px 6px 17px 2px rgba(140,140,140,1);
  box-shadow: 6px 6px 17px 2px rgba(140,140,140,1);
  img {
    width: 100%;
    height: 200px;
    object-fit: contain;
  }
}

.buttom-link {
  transition: 0.5s;
  text-decoration: none;
  color: white;
  background-color: white;
  color: #65A3AE;
  padding: 6px 15px;
  border-radius: 18px;
  -webkit-box-shadow: 2px 6px 8px 1px rgba(140,140,140,0.4);
  -moz-box-shadow: 2px 6px 8px 1px rgba(140,140,140,0.4);
  box-shadow: 2px 6px 8px 1px rgba(140,140,140,0.4);
  &:hover {
    background-color: #65A3AE;
    color: white;
  }
}

.side-tag {
  left: -5%;
  bottom: 25%;
  .smallArrow {
    margin-left: 10px;
    margin-right: 10px;
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

</style>
