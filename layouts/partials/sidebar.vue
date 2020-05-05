<template>
  <div class="sidebar">
    <!-- recent posts -->
    <h3>Posts Recientes</h3>
    <div class="widget lista">
      <recientes/>
    </div>
    <!-- search blog -->
    <!-- <h3>Buscar</h3>
    <div class="widget">
      <buscador/>
    </div> -->
    <!-- publicidad -->
    <h3>Productos Destacados</h3>
    <div class="widget">
      <publicidad/>
    </div>
    <!-- SOCIAL -->
    <h3>Compartir</h3>
    <div class="widget">
      <socials :titulo="titular" :url="SocialUrl"/>
    </div>
    <!-- SERVICIOS -->
    <h3>Servicios</h3>
    <div class="widget lista">
      <solser modo="servicios"/>
    </div>
    <!-- SOLUCIONES -->
    <h3>Soluciones</h3>
    <div class="widget lista">
      <solser modo="soluciones"/>
    </div>
  </div>
</template>

<script>
import buscador from '../partials/widgets/buscador.vue'
import publicidad from '../partials/widgets/publicidad.vue'
import recientes from '../partials/widgets/recientes.vue'
import socials from '../partials/widgets/socials.vue'
import solser from '../partials/widgets/soluciones-servicios.vue'

export default {
  components: {
    buscador,
    publicidad,
    recientes,
    socials,
    solser
  },
  props: {
    titular: String
  },
  computed: {
    SocialUrl: function () {
      return 'https://www.mechatronik-group.com/' + this.$route.fullPath
    }
  }
}
</script>

<style lang="scss">
  .sidebar {
    display: block;
    width: 100%;
    h3 {
      color: #65A3AE;
      text-align: left;
      border-bottom: 1px solid gray;
      padding-bottom: 5px;
      padding-top: 5px;
      text-transform: uppercase;
    }
    ul {
      list-style: none;
      padding: 0;
      li {
        margin-top: 15px;
        margin-bottom: 15px;
        a {
          transition: 0.5s;
          text-decoration: none;
          color: gray;
          &:hover {
            color: #65A3AE;
          }
        }
        h3 {
          color: white;
        }
      }
    }
    .lista {
      a {
        &::before {
              display: inline-block;
              //content: "&#8594;";
              content: "\203A";
              position: relative;
              bottom: 2px;
              margin-right: 5px;
              color: gray;
          }
      }
    }
  }

  .social-list {
  img {
    transition: 0.5s;
    width: 100%;
    cursor: pointer;
    &:hover {
      background-color: #e8e8e8;
    }
  }
}
</style>
