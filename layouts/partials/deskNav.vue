<template>
  <div class="desk">
   <nuxt-link to="/" id="desk-logo"><img class="logo" src="@/assets/images/identity/MECHATRONIK-WEB-LOGO-COLOR.png" alt="Mechatronik"> </nuxt-link>
   <!-- <a href="#">Español &#9660</a> -->
   <nuxt-link to="/compañia">COMPAÑIA</nuxt-link>
   <!-- <nuxt-link to="/soluciones">SOLUCIONES</nuxt-link> -->
   <div class="dropdown">
    <button class="dropbtn">SERVICIOS & SOLUCIONES
      <i class="fa fa-caret-down"></i>
    </button>
<div class="dropdown-content">
      <h4>SERVICIOS & SOLUCIONES</h4>
      <div class="men-grid">
        <div class="men-col">
        <nuxt-link class="big-links" to="/soluciones-servicios">
          <h5 class="link-tit">Acerca de</h5>
          <p class="link-sub link-desc">Desarrollamos proyectos llave en mano enfocados en la automatización de sus procesos de manufactura.
            Soluciones de sistema para aplicaciones de alto rendimiento.</p>
          <!-- <img  class="menu-img" src="../../assets/images/Soluciones/fondo-1.jpg"> -->
        </nuxt-link>
        </div>
        <div class="men-col">
        <nuxt-link class="big-links marg" to="/servicios">
          <h5 class="link-tit">Servicios</h5>
          <p class="link-sub link-item">Diseño Mecánico</p>
          <p class="link-sub link-item">Diseño Eléctrico</p>
          <p class="link-sub link-item">Manufactura Aditiva</p>
          <p class="link-sub link-item">Ingenieria de Control</p>
        </nuxt-link>
        </div>
        <div class="men-col">
        <nuxt-link class="big-links" to="/soluciones">
          <h5 class="link-tit">Soluciones</h5>
          <p class="link-sub link-item">Outsourcing de Personal</p>
          <p class="link-sub link-item">Consultoría en Industria 4.0</p>
          <p class="link-sub link-item">Consultoría en Motion Control</p>
        </nuxt-link>
        </div>
      </div>
    </div>
  </div>
  <div class="dropdown">
    <button class="dropbtn">PRODUCTOS
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="dropdown-content">
      <h4>PRODUCTOS</h4>
      <div class="men-grid">
        <div class="men-col">
        <nuxt-link class="big-links" to="/productos">
          <h5 class="link-tit">Todos Nuestros Productos</h5>
          <p class="link-sub link-desc">Nuestros porductos unen las mejores propiedades entre economia y rendimiento,
            estamos dedicados a un excelente soporte al clientes, A través, de nuestro catálogo podras conseguir informacion a profundidad.</p>
          <!-- <img  class="menu-img" src="../../assets/images/product-section/menu.jpg"> -->
        </nuxt-link>
        </div>
        <div class="men-col flexi marg">
          <nuxt-link to="/categorias" class="link-tit"><h5 class="link-tit">Categorias</h5></nuxt-link>
            <p class="link-sub" v-if="categorias == undefined">Empty</p>
            <nuxt-link class="link-item" v-else :to="'/categorias/'+ categoria.slug" v-for="categoria in categorias" v-bind:key="categoria.id"><p class="link-sub">{{categoria.name}}</p></nuxt-link>
        </div>
        <div class="men-col flexi">
          <nuxt-link to="/marcas" class="link-tit"><h5 class="link-tit">Marcas</h5></nuxt-link>
            <p class="link-sub" v-if="marcas == undefined">Empty</p>
            <nuxt-link class="link-item" v-else :to="'/marcas/'+ marca.slug" v-for="marca in marcas" v-bind:key="marca.id"><p class="link-sub">{{marca.name}}</p></nuxt-link>
        </div>
      </div>
    </div>
  </div>
   <nuxt-link to="/">INICIO</nuxt-link>
  </div>
</template>

<script>

export default {
    data: function() {
      return {
        categorias: null,
        marcas: null
      }
    },
    beforeMount: async function() {
        try {
          var Category = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products/categories?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f');
          var Brand = await this.$axios.get('https://blog.mechatronik-group.com/wp-json/wc/v3/products/tags?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f');
          this.categorias = Category.data;
          this.marcas = Brand.data;
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
  margin-left: 18px;
  margin-right: 18px;
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
 padding-right: 25px;
 font-family: Raleway;
 -webkit-box-shadow: 0px 14px 15px 0px rgba(0,0,0,0.34);
 -moz-box-shadow: 0px 14px 15px 0px rgba(0,0,0,0.34);
 box-shadow: 0px 14px 15px 0px rgba(0,0,0,0.34);
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
  font-family: Raleway;
  font-style: normal;
  font-weight: bold;
 }
 /* The dropdown container */
 .dropdown {
   transition: 0.5s;
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
   padding: 14px 16px;
   background-color: inherit;
   font: inherit; /* Important for vertical align on mobile phones */
   margin: 0; /* Important for vertical align on mobile phones */
   font-family: Raleway;
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

/* Add a red background color to navbar links on hover */
.desk a:hover, .dropdown:hover .dropbtn {
 color: white;
 background-color: rgba(101, 163, 174, 0.8);
 &#desk-logo {
   background-color: transparent;
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

/* Add a red background color to navbar links on hover */
.navbar a:hover, .dropdown:hover .dropbtn {
  color: white;
  background-color: rgba(101, 163, 174, 0.8);
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
    width: 90%;
    margin-left: 5%;
    margin-right: 5%;
    .marg {
      border-left: 1px solid #87888a;
      border-right: 1px solid #87888a;
    }
    .men-col {
      display: flex;
      flex-flow: column;
      a {
        float: none;
        color: white;
        text-decoration: none;
        display: block;
        height: auto;
        text-align: left;
      }
      a:hover {
        background-color: #65A3AE;
      }
      .link-item {
        margin-left: 10px;
        margin-right: 10px;
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
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    font-size: 24px;
    margin-left: 5%;
    }

  .menu-img {
      width: 100%;
      margin-bottom: 10px;
    }

    .link-tit {
      font-family: Raleway;
      font-style: normal;
      font-weight: bold;
      font-size: 18px;
      padding-top: 5px;
      padding-bottom: 5px;
      color: #87888a;
    }
    .link-sub {
      font-family: Raleway;
      font-style: normal;
      font-weight: lighter;
      padding-top: 2px;
      padding-bottom: 2px;
      text-align: justify;
      color: black;
      font-size: 12px;
      line-height: 1.35;
    }
}

/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {
  display: block;
}

</style>
