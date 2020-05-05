<template>
  <div class="product-displayer">
    <div class="section">
      <div class="product--display">
        <div class="nav-history"><a href="https://mechatronik-group.com/">Inicio</a> &#10095 <a href="https://mechatronik-group.com/productos">Productos</a> &#10095 {{producto.name}}</div>
        <div class="frame">
          <div class="product">
            <div class="image-displayer">
              <carousel class="carrousel" :perPage="1" :paginationEnabled="true" paginationActiveColor="#65A3AE">
                <slide class="slide" v-for="foto in producto.images" v-bind:key="producto.id">
                  <img :src="foto.src" alt="product picture">
                </slide>
              </carousel>
            </div>
            <div class="info">
              <h1>{{producto.name}}</h1>
              <h4 v-if="producto.acf != null">{{producto.acf.modelo}}</h4>
              <p v-html="producto.short_description"></p>
              <div class="complement-section">
                <div class="product--accordion">

                  <button class="accordion ac1" v-bind:class="{ active: acDes }" v-on:click="acDes = !acDes">Descripción</button>
                  <div class="panel left" v-bind:class="{ active: acDes }">
                    <p v-if="producto.acf != null" v-html="producto.description"></p>
                  </div>

                  <button class="accordion" v-bind:class="{ active: acEs }" v-on:click="acEs = !acEs">Especificaciones técnicas</button>
                  <div class="panel" v-bind:class="{ active: acEs }">
                    <div class="especificacion" v-for="(n) in especificaciones.length">
                      <div class="divisor">
                        <div>
                          <label>{{especificaciones[n-1]}}:</label>
                        </div>
                        <div>
                          {{detalles[n-1]}}
                        </div>
                      </div>
                    </div>
                  </div>

                  <button class="accordion" v-bind:class="{ active: acAp }" v-on:click="acAp = !acAp">Aplicaciones </button>
                  <div class="panel" v-bind:class="{ active: acAp }">
                    <p v-if="producto.acf != null" v-html="producto.acf.aplicaciones"></p>
                  </div>

                  <button class="accordion ac3" v-bind:class="{ active: acBro }" v-on:click="acBro = !acBro">Información técnica</button>
                  <div class="panel" v-bind:class="{ active: acBro }">
                    <p> <a v-if="producto.acf != null" :href="producto.acf.manual" target="_blank">Descargar Manual</a> </p>
                  </div>

                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="producto-relacionados" v-if="producto.categories != undefined">
          <!-- <relacionados :categoria="producto.categories.id" /> -->
          <h2>Productos relacionados</h2>
          <!-- <relacionados :categoria="36" /> -->
          <relacionados :categoria="producto.categories[0].id" />
        </div>
      </div>
    </div>
    <!-- <div class="complement-section">
      <div class="product--accordion">

        <button class="accordion ac1" v-bind:class="{ active: acDes }" v-on:click="acDes = !acDes">Descripción</button>
        <div class="panel" v-bind:class="{ active: acDes }">
          <p v-if="producto.acf != null" v-html="producto.description"></p>
        </div>

        <button class="accordion" v-bind:class="{ active: acEs }" v-on:click="acEs = !acEs">Especificaciones técnicas</button>
        <div class="panel" v-bind:class="{ active: acEs }">
          <div class="especificacion" v-for="(n) in especificaciones.length">
            <div class="divisor">
              <div>
                <label>{{especificaciones[n-1]}}:</label>
              </div>
              <div>
                {{detalles[n-1]}}
              </div>
            </div>
          </div>
        </div>

        <button class="accordion" v-bind:class="{ active: acAp }" v-on:click="acAp = !acAp">Aplicaciones </button>
        <div class="panel" v-bind:class="{ active: acAp }">
          <p v-if="producto.acf != null" v-html="producto.acf.aplicaciones"></p>
        </div>

        <button class="accordion ac3" v-bind:class="{ active: acBro }" v-on:click="acBro = !acBro">Información técnica</button>
        <div class="panel" v-bind:class="{ active: acBro }">
          <p> <a v-if="producto.acf != null" :href="producto.acf.manual" target="_blank">Descargar Manual</a> </p>
        </div>

      </div>
    </div> -->
  </div>
</template>

<script>
import relacionados from '../partials/widgets/productos.vue'

export default {
  components: {
    relacionados
  },
  data: function () {
    return {
      producto: {},
      especificaciones: [],
      detalles: [],
      acEs: false,
      acDes: false,
      acAp: false,
      acBro: false,
      isLoading: true
    }
  },
  mounted: async function() {
      try {
        const slug = this.$route.params.slug;
        var consulta;
        var parts;
        var jobj;
        var i = 0;
        consulta = 'https://blog.mechatronik-group.com/wp-json/wc/v3/products?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&slug=';
        consulta = consulta.concat(slug);
        var Producto = await this.$axios.get(consulta);
        this.producto = Producto.data[0];
        parts = this.producto.acf.atributos.split(';');
        for(i=0; i < parts.length; i+=2){
          //jobj[parts[i]]=parts[i+1];
          this.especificaciones.push(parts[i]);
          this.detalles.push(parts[i+1]);
        };
        this.isLoading = false;
      } catch (e) {
        this.isLoading = false;
        console.log(e);
      }
  },
}
</script>

<style lang="scss" scoped>

.section {
  text-align: left;
  @media (min-width: 1000px) {

  }
}

.left {
  text-align: justify;
}

.product-displayer {
  padding: 40px 0;
}

.producto-relacionados {
  h2 {
    font-size: calc(35px + (50 - 35) * ((100vw - 300px) / (1600 - 300)));
    font-family: 'OpenSans', Fallback, sans-serif;
    font-style: normal;
    font-weight: normal;
  }
}

.nav-history {
}

.divisor {
  width: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding: 8px 8px;
}

.complement-section {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  margin-bottom: 10%;
}

.product--display {
  width: 90%;
}

.frame {
  width: 100%;
  position: relative;
}

.product {
  width: 100%;
  display: grid;
  grid-template-columns: 100%;
  line-height: 1.5;
  @media (min-width: 1000px) {
    grid-template-columns: 50% 50%;
  }
  .info {
    display: flex;
    justify-content: flex-start;
    align-items: flex-start;
    flex-flow: column;
    text-align: justify;
    padding: 10%;
    h1 {
      margin: 0;
    }
    h4 {
      color: gray;
      font-weight: normal;
      margin-top: 10px;
      margin-bottom: 10px;
    }
    p {
      margin: 0;
    }
  }
}

.especificacion {
  text-align: left;
  width: 100%;
  label {
    font-weight: 600;
    display: inline-block;
    width: 44%;
    line-height: 1.2em;
    padding: 3px 5px 3px 0;
  }
  &:nth-child(2n) {
    background-color: #f9f9f9;
  }
}


.image-displayer {
  margin-top: 10%;
  width: 100%;
  height: 100%;
}

.carrousel {
  height: 250px;
  width: 250px;
  margin-left: auto;
  margin-right: auto;
  @media (max-width: 1000px) {
    grid-row: 1 / 1;
  }
  @media (min-width: 400px) {
    height: 300px;
    width: 300px;
  }
  @media (min-width: 700px) {
    height: 500px;
    width: 500px;
  }
}
.slide {
  height: 100%;
  width: 100%;
  background-size: cover;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  text-align: left;
  p {
    width: 90%;
    margin-left: 5%;
    margin-right: 5%;
    font-size: 12px;
    @media (min-width: 400px) {
      font-size: 1em;
    }
    @media (min-width: 600px) {
      width: 50%;
      margin-left: 10%;
    }
  }
  img {
    height: 250px;
    width: 250px;
    object-fit: cover;
    @media (min-width: 400px) {
      height: 300px;
      width: 300px;
    }
    @media (min-width: 700px) {
      height: 500px;
      width: 500px;
    }
  }
}

.side-tag {
  left: -5%;
  .smallArrow {
    margin-left: 10px;
    margin-right: 10px;
  }
}

.product--accordion {
  margin-top: 25px;
  width: 100%;
  border: 1px lightgray solid;
  //filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
}

/* Style the buttons that are used to open and close the accordion panel */
.accordion {
 background-color: white;
 color: #444;
 cursor: pointer;
 padding: 18px;
 width: 100%;
 text-align: left;
 border: none;
 outline: none;
 transition: 0.4s;
 border-bottom: 1px lightgray solid;
   &:hover {
     background-color: #ccc;
   }
   &:after {
     content: '\23F7'; /* Unicode character for "plus" sign (+) */
     font-size: 20px;
     color: #65A3AE;
     float: right;
     margin: 0;
     margin-left: 5px;
   }
   &.active {
     display: block;
     &:after {
       content: "\23F6"; /* Unicode character for "minus" sign (-) */
     }
   }
}



/* Style the accordion panel. Note: hidden by default */
.panel {
 padding: 0 18px;
 background-color: white;
 display: block;
 overflow: hidden;
 padding: 0 18px;
 max-height: 0;
 transition: max-height 0.3s ease-out;
 a {
   text-decoration: none;
   color: #65A3AE;
 }
 &.active {
   //display: block;
   max-height: 100vh;
 }
}
</style>
