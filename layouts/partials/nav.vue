<template>
<div id="navigation" v-bind:class="{ home: ishome }">
  <div class="black-label">
    <nuxt-link to="/blog">Blog</nuxt-link>
    <!-- <a href="#">Partners</a> -->
    <a href="#" v-scroll-to="'#contact'">Contacto</a>
  </div>
  <mobileNav v-bind:class="{ home: ishome }"/>
  <deskNav v-bind:class="{ home: ishome }"/>
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
  position: sticky; /* Set the navbar to fixed position */
  top: 0; /* Position the navbar at the top of the page */
  width: 100%;
  z-index: 50;
  &.home {
    position: fixed; /* Set the navbar to fixed position */
    top: 0; /* Position the navbar at the top of the page */
    width: 100%;
    z-index: 50;
  }
}

.logo {
  height: 50%;
}

.bar {
  overflow: hidden;
  width: 100%;
  background-color: white;

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
