<template>
  <div>
    <div class="section">
      <div class="product--display">
        <div class="frame">
          <div class="product">
            <div class="info">
              <h1>{{producto.nombre}}</h1>
              <h4>{{producto.modelo}}</h4>
              <p v-html="producto.descripcion"></p>
            </div>
            <carousel class="carrousel" :perPage="1" :paginationEnabled="true" paginationActiveColor="#65A3AE">
              <slide class="slide" v-for="foto in fotos" v-bind:key="producto.id">
                <img :src="foto" alt="product picture">
              </slide>
            </carousel>
          </div>
          <div class="side-tag"> <span>&#9472&#9472&#9472</span>Productos <span class="smallArrow">&#10095;</span> {{producto.marca}}</div>
        </div>
      </div>
    </div>
    <div class="complement-section">
      <div class="product--accordion">

        <button class="accordion" v-bind:class="{ active: acEs }" v-on:click="acEs = !acEs">Especificaciones técnicas</button>
        <div class="panel" v-bind:class="{ active: acEs }">
          <div class="especificacion" v-for="(n) in especificaciones.length">
            <label>{{especificaciones[n-1]}}:</label> {{detalles[n-1]}}
          </div>
        </div>

        <button class="accordion" v-bind:class="{ active: acAp }" v-on:click="acAp = !acAp">Aplicaciones </button>
        <div class="panel" v-bind:class="{ active: acAp }">
          <p v-html="producto.aplicaciones"></p>
        </div>

        <button class="accordion" v-bind:class="{ active: acBro }" v-on:click="acBro = !acBro">Información técnica</button>
        <div class="panel" v-bind:class="{ active: acBro }">
          <p> <a :href="producto.folleto" target="_blank">Descargar Manual</a> </p>
        </div>

      </div>
    </div>
  </div>
</template>

<script>

export default {
  data: function () {
    return {
      producto: {},
      fotos: [],
      especificaciones: [],
      detalles: [],
      acEs: false,
      acAp: false,
      acBro: false,
      isLoading: true
    }
  },
  mounted: async function() {
      try {
        const id = this.$route.params.id;
        var consulta;
        var parts;
        var jobj;
        var i = 0;
        consulta = 'http://mechatronik-group.com:4000/api/producto/';
        consulta = consulta.concat(id);
        var Producto = await this.$axios.get(consulta);
        this.producto = Producto.data.productos[0];
        this.fotos = Producto.data.productos[0].fotos.split(';');
        parts = this.producto.especificaciones.split(';');
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
  margin-top: 110px;
  @media (min-width: 1000px) {
    margin-top: 140px;
  }
}

.complement-section {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  margin-bottom: 10%;
}

.product--display {
  width: 80%;
}

.frame {
  width: 100%;
  position: relative;
}

.product {
  width: 100%;
  display: grid;
  grid-template-columns: 100%;;
  @media (min-width: 1000px) {
    grid-template-columns: 50% 50%;
  }
  .info {
    display: flex;
    justify-content: center;
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
  width: 85%;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
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
