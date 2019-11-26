<template>
<div id="navigation">
  <div class="black-label">
    <!-- <a href="#">Blogs</a>
    <a href="#">Partners</a> -->
    <a href="#" v-scroll-to="'#contact'">Contacto</a>
  </div>
  <mobileNav v-bind:class="{ home: ishome }"/>
  <deskNav v-bind:class="{ home: ishome }"/>
  <!-- <div class="desk" v-bind:class="{ home: ishome }">
   <nuxt-link to="/" id="desk-logo"><img class="logo" src="@/assets/images/identity/MECHATRONIK-WEB-LOGO-COLOR.png" alt="Mechatronik"> </nuxt-link>
   <a href="#">Español &#9660</a>
   <nuxt-link to="/compañia">COMPAÑIA</nuxt-link>
   <div class="dropdown">
     <button class="dropbtn">PRODUCTOS Y SOLUCIONES
       <i class="fa fa-caret-down"></i>
     </button>
     <div class="dropdown-content">
       <div class="row">
         <div class="column">
           <nuxt-link to="/productos-y-soluciones">
             <h3>PRODUCTOS Y SOLUCIONES</h3>
             <p>
               Our leading Industrial Innovation platform and solutions
               turn possibility into a reality.
             </p>
           </nuxt-link>
         </div>
         <div class="column">
           <nuxt-link to="/soluciones">
             <h3>SOLUCIONES</h3>
             <h4>Experiencia Insudtrial</h4>
             <ul>
               <li>Proyectos especiales llave en mano orientados a la industria 4.0</li>
               <li>Servosistemas</li>
               <li>Robótica industrial para aplicaciones de ensamble e inspección</li>
               <li>Trazabilidad de líneas de producció</li>
               <li>Líneas de inspección</li>
             </ul>
             <h4>Aplicaciones </h4>
             <ul>
               <li>Speed Positioning</li>
               <li>Continuous Operation</li>
               <li>Synchronous Operation</li>
               <li>Product Handling</li>
               <li>Numeric Control</li>
             </ul>
           </nuxt-link>
         </div>
         <div class="column servicios">
          <nuxt-link to="/servicios">
             <h3>SERVICIOS</h3>
             <h4>Diseño Mecánico</h4>
             <ul>
               <li>Diseño Eléctrico</li>
               <li>Manufactura Aditiva</li>
               <li>Ingeniería de Control</li>
             </ul>
             <h4>Algunas otras </h4>
             <ul>
               <li>Outsourcing de Personal</li>
               <li>Consultoría en Industria 4.0</li>
               <li>Consultoría en Motion Control</li>
             </ul>
          </nuxt-link>
         </div>
         <div class="column">
          <nuxt-link to="/productos">
             <h3>PRODUCTOS</h3>
             <h4>Products Overview</h4>
             <ul>
               <li>Servo Gearboxes</li>
               <li>Couplings </li>
               <li>Actuators</li>
               <li>Screw Jack systems</li>
               <li>Grippers</li>
               <li>Index table</li>
             </ul>
             <h4>Brands Overview</h4>
             <ul>
               <li>Neugart</li>
               <li>R+W</li>
               <li>Festo</li>
               <li>Zimm</li>
               <li>Zimmer group</li>
               <li>Weiss</li>
             </ul>
            </nuxt-link>
         </div>
       </div>
     </div>
   </div>
   <nuxt-link to="/">INICIO</nuxt-link>
  </div> -->
</div>
</template>

<script>

import mobileNav from '~/layouts/partials/movileNav.vue'
import deskNav from '~/layouts/partials/deskNav.vue'

if (process.client) {
  // The debounce function receives our function as a parameter
const debounce = (fn) => {
  // This holds the requestAnimationFrame reference, so we can cancel it if we wish
  let frame;
  // The debounce function returns a new function that can receive a variable number of arguments
  return (...params) => {
    // If the frame variable has been defined, clear it now, and queue for next frame
    if (frame) {
      cancelAnimationFrame(frame);
    }
    // Queue our function call for the next frame
    frame = requestAnimationFrame(() => {
      // Call our function and pass any params we received
      fn(...params);
    });
  }
};
// Reads out the scroll position and stores it in the data attribute
// so we can use it in our stylesheets
const storeScroll = () => {
  document.documentElement.dataset.scroll = window.scrollY;
}
// Listen for new scroll events, here we debounce our `storeScroll` function
document.addEventListener('scroll', debounce(storeScroll), { passive: true });
// Update scroll position for first time
storeScroll();
}

export default {
  components: {
    mobileNav,
    deskNav
  },
  data: function() {
    return {
      ishome: false
    }
  },
  watch: {
    '$route.path':  function(path) {
      if (path== "/") {
        this.ishome = true;
      }
      else {
        this.ishome = false;
      }
    }
  },
  mounted: function () {
    if (this.$route.path == "/") {
      this.ishome = true;
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

.black-label {
  width: 100%;
  background: black;
  color: white;
  text-align: right;
  padding: 10px;
  padding-right: 3%;
  a {
    transition: 0.5s;
    color: white;
    text-decoration: none;
    margin-left: 15px;
    font-size: 12px;
    &:hover {
      color: #65A3AE;
    }
  }
}
</style>
