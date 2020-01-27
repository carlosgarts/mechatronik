<template>
<div class="mobile">
   <nuxt-link to="/" id="mob-logo"><img class="logo" src="@/assets/images/identity/MECHATRONIK-WEB-LOGO-COLOR.png" alt="Mechatronik"> </nuxt-link>
   <div class="dropdown">
     <button class="dropbtn" v-on:click="is_toggled = !is_toggled">
       <svg id="hamburger" v-bind:class="{ toggled: is_toggled }" ishome version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
       	 viewBox="0 0 228 173.3" style="enable-background:new 0 0 228 173.3;" xml:space="preserve">
       <style type="text/css">
       	.st0{fill:#65A3AE;}
       </style>
       <path id="meat" class="st0" d="M199.7,97.7H37c-6,0-11-4.9-11-11v0c0-6,4.9-11,11-11h162.7c6.1,0,11,4.9,11,11v0
       	C210.7,92.7,205.7,97.7,199.7,97.7z"/>
       <path id="bun2" class="st0" d="M199.7,141H37c-6,0-11-4.9-11-11v0c0-6,4.9-11,11-11h162.7c6.1,0,11,4.9,11,11v0
       	C210.7,136.1,205.7,141,199.7,141z"/>
       <path id="bun1" class="st0" d="M199.7,54.3H37c-6,0-11-4.9-11-11v0c0-6,4.9-11,11-11h162.7c6.1,0,11,4.9,11,11v0
       	C210.7,49.4,205.7,54.3,199.7,54.3z"/>
       </svg>
     </button>
     <div class="dropdown-content" v-bind:class="{ toggled: is_toggled }" >
       <div class="row" @click="is_toggled = false">
         <nuxt-link to="/">
           <h3>INICIO</h3>
         </nuxt-link>
       </div>
         <div class="row" @click="is_toggled = false">
           <nuxt-link to="/marcas">
             <h3>MARCAS</h3>
             <p>
               Our leading Industrial Innovation platform and solutions
               turn possibility into a reality.
             </p>
           </nuxt-link>
         </div>
         <div class="row" @click="is_toggled = false">
           <nuxt-link to="/categorias">
             <h3>PRODUCTOS</h3>
             <p>
               Our leading Industrial Innovation platform and solutions
               turn possibility into a reality.
             </p>
           </nuxt-link>
         </div>
         <div class="row" @click="is_toggled = false">
           <nuxt-link to="/soluciones">
             <h3>SOLUCIONES</h3>
             <p>Experiencia Insudtrial & Aplicaciones</p>
           </nuxt-link>
         </div>
         <div class="row" @click="is_toggled = false">
          <nuxt-link to="/servicios">
             <h3>SERVICIOS</h3>
               <p>Diseño Mecánico y otras</p>
          </nuxt-link>
         </div>
         <div class="row nbb" @click="is_toggled = false">
          <nuxt-link to="/compañia">
             <h3>COMPAÑIA</h3>
               <p>Quienes somos </p>
          </nuxt-link>
         </div>
     </div>
   </div>
</div>
</template>

<script>

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
  data: function() {
    return {
      ishome: false,
      is_toggled: false
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

#hamburger {
  height: 100%;
}

.logo {
  height: 50%;
}

#mob-logo {
  float: left;
  margin: 0;
  padding: 0;
  margin-left: 15px;
}

.bar {
  overflow: hidden;
  width: 100%;
  background-color: white;
}

/* Navbar container */
.mobile {
 transition: 0.5s;
 overflow: hidden;
 background-color: white;
 color: #050505;
 height: 70px;
 //padding-right: 25px;
 -webkit-box-shadow: 0px 14px 15px 0px rgba(0,0,0,0.34);
 -moz-box-shadow: 0px 14px 15px 0px rgba(0,0,0,0.34);
 box-shadow: 0px 14px 15px 0px rgba(0,0,0,0.34);
 @media (min-width: 1000px) {
   display: none;
 }
 a {
  transition: 0.5s;
  display: flex;
  justify-content: center;
  align-items: center;
  float: right;
  height: 100%;
  font-size: 16px;
  color: #050505;
  text-align: center;
  //padding: 14px 16px;
  padding-left: 18px;
  padding-right: 18px;
  text-decoration: none;

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
   cursor: pointer;
   border: none;
   outline: none;
   height: 100%;
   padding: 14px 16px;
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
  .home {
    background-color: transparent;
    -webkit-box-shadow: none;
    -moz-box-shadow: none;
    box-shadow: none;
    a {
      color: white;
    }
    .st0 {
        fill: white;
    }
    .dropdown {
         .dropbtn {
         color: white;
         }
       }
  }
}

.home {
  .st0 {
      fill: #65A3AE;
  }
}

/* Links inside the navbar */


/* Dropdown content (hidden by default) */
.dropdown-content {
 display: flex;
 flex-flow: column;
 border-top: 1px solid #CCCCCC;
 visibility: hidden;
 position: absolute;
 background: white;
 width: 100%;
 height: 100vh;
 left: 0;
 z-index: 1;
 opacity: 0;
 transition: visibility 0s, opacity 0.2s linear;
 padding: 25px;
 box-shadow: 0px 8px 8px 0px rgba(0,0,0,0.2);
}

#bun1, #meat, #bun2 {
  transition: 0.5s;
}

/* Show the dropdown menu on hover */
.toggled {
  &.dropdown-content {
    visibility: visible;
    opacity: 1;
  }
  &#hamburger {
    #bun1 {
      transform-origin: 55% 100%;
      transform:  translateY(11%) translateX(-50%) rotate(45deg);
    }
    #meat {
      opacity: 0;
    }
    #bun2 {
      transform-origin: 55% 100%;
      transform:  translateY(-30%) rotate(-45deg);
    }
  }
}


/* Create three equal columns that floats next to each other */
.row {
 float: left;
 width: 100%;
 padding: 10px;
 border-bottom: 1px solid #65A3AE;
 //height: 250px;
 &.nbb {
   border-bottom: none;
 }
 a {
   float: none;
   text-decoration: none;
   display: block;
   text-align: left;
 }
 a:hover {
  background-color: #ddd;
 }
 h3 {
   color: #65A3AE;
   margin-bottom: 5px;
   text-align: left;
 }
 h4 {

 }
 p {
   font-size: 12px;
   margin: 5px;
 }
 ul {

 }
 li {
   list-style: none;
 }
}


/* Clear floats after the columns */
.row:after {
 content: "";
 display: table;
 clear: both;
}

//////Menu language//////////////////////////////////////////////////////

</style>
