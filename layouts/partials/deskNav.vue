<template>
  <div class="desk">
   <nuxt-link to="/" id="desk-logo"><img class="logo" src="@/assets/images/identity/MECHATRONIK-WEB-LOGO-COLOR.png" alt="Mechatronik"> </nuxt-link>
   <!-- <a href="#">Español &#9660</a> -->
   <nuxt-link to="/compañia">COMPAÑIA</nuxt-link>
   <nuxt-link to="/soluciones">SOLUCIONES</nuxt-link>
   <div class="dropdown">
    <button class="dropbtn">SERVICIOS
      <i class="fa fa-caret-down"></i>
    </button>
<div class="dropdown-content">
      <h4>SERVICIOS</h4>
      <nuxt-link class="big-links mb" to="/servicios">
        <h5 class="link-tit">Experiencia Industrial</h5>
        <p class="link-sub">Diseño Mecánico</p>
        <p class="link-sub">Diseño Eléctrico</p>
        <p class="link-sub">Manufactura Aditiva</p>
        <p class="link-sub">Ingenieria de Control</p>
      </nuxt-link>
      <nuxt-link class="big-links" to="/servicios">
        <h5 class="link-tit">Algunas otras</h5>
        <p class="link-sub">Outsourcing de Personal</p>
        <p class="link-sub">Consultoría en Industria 4.0</p>
        <p class="link-sub">Consultoría en Motion Control</p>
      </nuxt-link>
    </div>
  </div>
  <div class="dropdown">
    <button class="dropbtn">PRODUCTOS
      <i class="fa fa-caret-down"></i>
    </button>
    <div class="dropdown-content">
      <h4>PRODUCTOS</h4>
      <nuxt-link to="/categorias" class="link-tit">Categorias</nuxt-link>
        <p class="link-sub" v-if="categorias == undefined">Empty</p>
        <nuxt-link v-else :to="'/categorias/'+ categoria.id" v-for="categoria in categorias" v-bind:key="categoria.id"><p class="link-sub">{{categoria.titulo}}</p></nuxt-link>
      <nuxt-link to="/marcas" class="link-tit">Marcas</nuxt-link>
        <p class="link-sub" v-if="marcas == undefined">Empty</p>
        <nuxt-link v-else :to="'/marcas/'+ marca.id" v-for="marca in marcas" v-bind:key="marca.id"><p class="link-sub">{{marca.titulo}}</p></nuxt-link>
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
          var Category = await this.$axios.get('http://mechatronik-group.com:4000/api/categorias');
          var Brand = await this.$axios.get('http://mechatronik-group.com:4000/api/marcas');
          this.categorias = Category.data.categorias;
          this.marcas = Brand.data.marcas;
        } catch (e) {
          this.isLoading = false;
          console.log(e);
        }
    }
}
</script>

<style lang="scss" scoped>

#navigation {
  position: fixed; /* Set the navbar to fixed position */
  top: 0; /* Position the navbar at the top of the page */
  width: 100%;
  z-index: 50;
}

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
  -webkit-box-shadow: 0px 14px 15px 0px rgba(0,0,0,0.34);
  -moz-box-shadow: 0px 14px 15px 0px rgba(0,0,0,0.34);
  box-shadow: 0px 14px 15px 0px rgba(0,0,0,0.34);
}

/* Navbar container */
.desk {
 display: none;
 transition: 0.5s;
 overflow: hidden;
 background-color: white;
 color: #050505;
 height: 100px;
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
  font-size: 14px;
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
  padding-bottom: 15px;
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

//////Menu language//////////////////////////////////////////////////////

/* The dropdown container */
.dropdown {
  float: left;
  overflow: hidden;
}

.dropbtn {
  transition: 0.5s;
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
  background-color: rgba(0,0,0,0.6);
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
  a {
    float: none;
    color: white;
    text-decoration: none;
    display: block;
    text-align: left;
    .link-sub {
      font-family: Raleway;
      font-style: normal;
      font-weight: lighter;
      padding-top: 2px;
      padding-bottom: 2px;
      padding-left: 10px;
    }
  }
  a:hover {
    background-color: #65A3AE;
  }
  .big-links {
    padding-top: 5px;
    padding-bottom: 5px;
    &.mb {
      border-bottom: 1px solid #65A3AE;
    }
  }
  h4 {
    color: #65A3AE;
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    font-size: 16px;
    }

    .link-tit {
      font-family: Raleway;
      font-style: normal;
      font-weight: bold;
      font-size: 16px;
      padding-top: 2;
      padding-bottom: 2;
    }
    .link-sub {
      font-family: Raleway;
      font-style: normal;
      font-weight: lighter;
      padding-top: 2px;
      padding-bottom: 2px;
      padding-left: 25px;
      color: white;
    }
}

/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {
  display: block;
}

</style>
