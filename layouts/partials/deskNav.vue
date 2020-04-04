<template>
  <div class="desk">
   <nuxt-link to="/" id="desk-logo"><img class="logo" src="@/assets/images/identity/MECHATRONIK-WEB-LOGO-COLOR.png" alt="Mechatronik"> </nuxt-link>
   <!-- <a href="#">Español &#9660</a> -->
   <nuxt-link class="desk-link" to="/compañia">COMPAÑIA</nuxt-link>
   <!-- <nuxt-link to="/soluciones">SOLUCIONES</nuxt-link> -->
   <div class="dropdown">
    <button class="dropbtn desk-link">SERVICIOS & SOLUCIONES
      <i class="fa fa-caret-down"></i>
    </button>
<div class="dropdown-content">
      <h4>SERVICIOS & SOLUCIONES</h4>
      <div class="men-grid">
        <div class="men-col">
          <div class="men-col flexi marg" v-if="servicios != undefined">
            <nuxt-link to="/servicios" class="link-tit"><h5>Servicios</h5></nuxt-link>
                <nuxt-link class="link-item" :to="'/servicios/'+ servicio.slug" v-for="servicio in servicios" v-if="servicio.categories == 18" v-bind:key="servicio.id"><p class="link-sub">{{servicio.title.rendered}} <span>&#10095</span></p></nuxt-link>
          </div>
        </div>
        <div class="men-col">
          <div class="men-col flexi marg" v-if="servicios != undefined">
            <nuxt-link to="/soluciones" class="link-tit"><h5>Soluciones</h5></nuxt-link>

                <nuxt-link class="link-item" :to="'/soluciones/'+ solucion.slug" v-for="solucion in servicios" v-if="solucion.categories == 19" v-bind:key="solucion.id"><p class="link-sub">{{solucion.title.rendered}} <span>&#10095</span></p></nuxt-link>

          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="dropdown">
    <button class="dropbtn desk-link">PRODUCTOS
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="dropdown-content">
      <h4>PRODUCTOS</h4>
      <div class="men-grid">
        <div class="men-col flexi marg">
          <nuxt-link to="/categorias" class="link-tit"><h5>Categorias</h5></nuxt-link>
            <p class="link-sub" v-if="categorias == undefined">Empty</p>
            <nuxt-link class="link-item" v-else :to="'/categorias/'+ categoria.slug" v-for="categoria in categorias" v-bind:key="categoria.id"><p class="link-sub">{{categoria.name}} <span>&#10095</span></p></nuxt-link>
        </div>
        <div class="men-col flexi">
          <nuxt-link to="/marcas" class="link-tit"><h5>Marcas</h5></nuxt-link>
            <p class="link-sub" v-if="marcas == undefined">Empty</p>
            <nuxt-link class="link-item" v-else :to="'/marcas/'+ marca.slug" v-for="marca in marcas" v-bind:key="marca.id"><p class="link-sub">{{marca.name}} <span>&#10095</span></p></nuxt-link>
        </div>
        <div class="men-col">
        <nuxt-link class="big-links" to="/productos">
          <h5>Todos Nuestros Productos</h5>
          <!-- <p class="link-sub link-desc">Nuestros porductos unen las mejores propiedades entre economia y rendimiento,
            estamos dedicados a un excelente soporte al clientes, A través, de nuestro catálogo podras conseguir informacion a profundidad.</p> -->
          <!-- <img  class="menu-img" src="../../assets/images/product-section/menu.jpg"> -->
        </nuxt-link>
        </div>
      </div>
    </div>
  </div>
   <nuxt-link class="desk-link" to="/">INICIO</nuxt-link>
  </div>
</template>

<script>

export default {
    data: function() {
      return {
        categorias: null,
        marcas: null,
        servicios: null
      }
    },
    beforeMount: async function() {
        try {
          var Category = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products/categories?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f');
          var Brand = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products/tags?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f');
          var Servicios = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wp/v2/posts?categories=18+19&filter[orderby]=date&order=asc');
          this.categorias = Category.data;
          this.marcas = Brand.data;
          this.servicios = Servicios.data;
        } catch (e) {
          this.isLoading = false;
          console.log(e);
        }
    }
}
</script>

<style lang="scss" scoped>

.logo {
  height: 50%;
}

#desk-logo {
  float: left;
  margin: 0;
  padding: 0;
  max-height: 100px;
  // margin-left: 18px;
  // margin-right: 18px;
}

.bar {
  overflow: hidden;
  width: 100%;
  background-color: white;
}

/* Navbar container */
.desk {
 display: none;
 transition: 0.5s;
 overflow: hidden;
 background-color: white;
 color: #050505;
 height: 70px;
 padding-right: 5%;
 padding-left: 5%;
 // -webkit-box-shadow: 0px 8px 8px 0px rgba(0,0,0,0.2);
 // -moz-box-shadow: 0px 8px 8px 0px rgba(0,0,0,0.2);
 // box-shadow: 0px 8px 8px 0px rgba(0,0,0,0.2);
 border-bottom: 2px solid #dfe6ed;
 @media (min-width: 1000px) {
   display: block;
 }
 a {
  transition: 0.5s;
  display: flex;
  justify-content: center;
  align-items: center;
  float: right;
  height: 100%;
  color: #050505;
  text-align: center;
  padding-left: 18px;
  padding-right: 18px;
  text-decoration: none;
  font-style: normal;
  font-weight: bold;
 }
 /* The dropdown container */
 .dropdown {
   transition: 0.5s;
   transition-timing-function: ease-in;
  float: right;
  overflow: hidden;
  height: 100%;
  .dropbtn {
   transition: 0.5s;
   font-size: 14px;
   border: none;
   outline: none;
   height: 100%;
   color: #050505;
   padding: 0px 16px;
   background-color: inherit;
   font: inherit; /* Important for vertical align on mobile phones */
   margin: 0; /* Important for vertical align on mobile phones */
   font-style: normal;
   font-weight: bold;
  }
 }
}
//html:not([data-scroll='0']) {

html[data-scroll='0'] {
  .desk {
    width: 100%;
    height: 100px;
  }
  .home {
    background-color: transparent;
    -webkit-box-shadow: none;
    -moz-box-shadow: none;
    box-shadow: none;
    border-bottom: none;
    a {
      color: white;
    }
    .dropdown {
         .dropbtn {
         color: white;
         }
       }
  }
}

/* Links inside the navbar */

.desk-link {
  position: relative;
  &:after {
    transition: 0.2s;
    content: '';
    display: block;
    width: 0%;
    height: 5px;
    background-color: rgba(101, 163, 174, 0.8);
    position: absolute;
    bottom: 0px;
    left: 0px;
  }
  &:hover{
    &:after{
      width: 100%;
    }
  }
}


/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {
  visibility: visible;
  opacity: 1;
  padding-left: 15px;
  padding-right: 15px;
  padding-bottom: 31px;
}


/* Create three equal columns that floats next to each other */
.column {
 float: left;
 width: 23%;
 padding: 10px;
 //height: 250px;
 a {
   float: none;
   color: white;
   padding: 16px;
   text-decoration: none;
   display: block;
   text-align: left;
 }
 a:hover {
  background-color: #ddd;
 }
}

.servicios {
  border-left: 1px solid #65A3AE;
  border-right: 1px solid #65A3AE;
}


/* Clear floats after the columns */
.row:after {
 content: "";
 display: table;
 clear: both;
}

/* Dropdown button */
.dropdown .dropbtn {
  font-size: 14px;
  border: none;
  outline: none;
  color: white;
  padding: 14px 16px;
  background-color: inherit;
  font-family: inherit; /* Important for vertical align on mobile phones */
  margin: 0; /* Important for vertical align on mobile phones */
}

/* Links inside the dropdown */
.dropdown-content {
  display: none;
  position: absolute;
  background-color: white;
  width: 100%;
  left: 0;
  border-top: 1px solid #CCCCCC;
  box-shadow: 0px 8px 8px 0px rgba(0,0,0,0.2);
  z-index: 1;
  .men-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-column-gap: 25px;
    width: 90%;
    margin-left: 5%;
    margin-right: 5%;

    .men-col {
      display: flex;
      flex-flow: column;
      a {
        float: none;
        color: gray;
        text-decoration: none;
        display: block;
        height: auto;
        text-align: left;
      }
      a:hover {
        text-decoration: underline;
        background-color: rgba(lightgray, 0.2);
        :after {

        }
      }
      .link-item {
        border-bottom: 1px solid #CCCCCC;
        position: relative;
        &:nth-child(1) {

        }
        span {
          position: absolute;
          right: 15px;
        }
      }
      .link-desc {
        margin-right: 10px;
      }
      .big-links {
        padding-top: 5px;
        padding-bottom: 5px;
        &.mb {
          border-bottom: 1px solid #65A3AE;
        }
      }
    }
  }
  h4 {
    color: #65A3AE;
    font-style: normal;
    font-weight: bold;
    font-size: 24px;
    margin-left: 5%;
    margin-bottom: 15px;
    }

  .menu-img {
      width: 100%;
      margin-bottom: 10px;
    }

    .link-tit {
      font-style: normal;
      font-weight: bold;
      font-size: 21px;
      padding-top: 0;
      padding-bottom: 0;
      color: #87888a;
      border-bottom: 1px solid #CCCCCC;
    }
    .link-sub {
      font-style: normal;
      font-weight: normal;
      text-align: justify;
      color: black;
      font-size: 16px;
      line-height: 1.35;
      margin-top: 7px;
      margin-bottom: 7px;
    }
}

h5 {
  color: #87888a;
  font-size: 21px;
}

/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {
  display: block;
}

</style>
