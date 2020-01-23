<template>
  <div class="container">
    <div id="productos--soluciones">
      <div class="title">
        <div class="title1">
          <h4>Productos<br>Soluciones</h4>
          <div class="ampersand">&</div>
        </div>
      </div>
      <div class="video-frame">
        <video class="video" autoplay muted loop>
           <source src="../assets/videos/machines.webm" type="video/webm">
          Your browser does not support the video tag.
        </video>
      </div>
      <div id="text--description">
        <img src="@/assets/images/test1.jpg" alt="motor">
        <p>Nuestro enfoque se adapta a las necesidades específicas de cada
          cliente y el sector donde se desempeña su negocio.
          Contamos con un amplio conjunto de servicios especializados,
          amplia experiencia en la ingeniería de automatización y
          gran capacidad diferencial para integrar nuevas tecnologías.</p>
      </div>
      <div id="title--lone">
          <h4>Soluciones<br>Servicios<br>Productos</h4>
      </div>
      <div id="text--lone">
        <div class="quote">
          <div id="t1" class="thick">“</div>
          <p>Desarrollamos proyectos llave en mano enfocados en la automatización de sus procesos de manufactura.</p>
          <div id="t2" class="thick">”</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  components: {

  }
}
</script>

<style lang="scss" scoped>
  .container {
    background: #65A3AE;
    overflow: hidden;
  }
  #productos--soluciones {
    display: grid;
    grid-template-columns: 15% 15% 40% 15% 15%;
    width: 100%;
    min-height: 130vh;
    margin-bottom: 20vh;
    @media (min-width: 800px) {
      grid-template-columns: 10% 26.6% 26.7% 26.7% 10%;
      grid-row-gap: 0;
    }
  }

  .title{
    grid-column-start: 2;
    grid-column-end: 5;
    @media (min-width: 800px) {
      grid-column-start: 2;
      grid-column-end: 4;
    }
    .title1 {
      display: inline-block;
      position: relative;
      height: auto;
      width: auto;
      h4{
        font-family: Raleway;
        font-style: normal;
        font-weight: 900;
        //font-size: 100px;
        font-size: calc(30px + (70 - 30) * ((100vw - 300px) / (1600 - 300)));
        color: #65A3AE;
        text-shadow: -1px 0 white, 0 1px white, 1px 0 white, 0 -1px white;
        text-align: left;
        line-height: 96.4%;
        margin-top: 50px;
        margin-bottom: 50px;
      }
      .ampersand {
        transition: 0.5s;
        position: absolute;
        top:0;
        right: -4vw;
        font-family: Raleway;
        color: rgba(255, 255, 255, 0.16);
        //font-size: 250px;
        font-size: calc(70px + (175 - 70) * ((100vw - 300px) / (1600 - 300)));
        font-weight: 900;
        line-height: 2;
        @media (min-width: 600px) {
          line-height: 1.5;
        }
        @media (min-width: 800px) {
          line-height: 1.3;
        }
      }
    }
  }

  .video-frame {
    grid-column-start: 1;
    grid-column-end: 6;
    @media (min-width: 800px) {
      grid-column-start: 2;
      grid-column-end: 4;
    }
    .video {
      width: 80%;
    }
  }

  #text--description {
    grid-column-start: 3;
    grid-column-end: 6;
    grid-row-start: 2;
    grid-row-end: 3;
    margin-bottom: 50px;
    @media (min-width: 800px) {
      grid-column-start: 4;
      grid-column-end: 6;
      grid-row-start: 1;
      grid-row-end: 3;
    }
    img {
      width: 100%
    }
    p {
      transition: 0.5s;
      margin-top: 18px;
      font-family: Raleway;
      font-style: normal;
      font-weight: normal;
      //font-size: 17px;
      font-size: calc(13px + (17 - 13) * ((100vw - 300px) / (1600 - 300)));
      //line-height: 28px;
      line-height: 1.5;
      width: 85%;
      color: #FFFFFF;
      @media (min-width: 800px) {
        margin-top: 30px;
      }
    }
  }

  #title--lone {
    grid-column-start: 2;
    grid-column-end: 4;
    display: flex;
    align-items: center;
    margin-bottom: 30px;
    @media (min-width: 800px) {
      grid-column-start: 2;
      grid-column-end: 3;
    }
    h4 {
      transition: 0.5s;
      font-family: Raleway;
      font-style: normal;
      font-weight: 900;
      //font-size: 49px;
      font-size: calc(30px + (55 - 30) * ((100vw - 300px) / (1600 - 300)));
      //line-height: 50px;
      line-height: 1.3;
      color: #78b2bd;
      text-shadow: -1px 0 white, 0 1px white, 1px 0 white, 0 -1px white;
      text-align: left;
    }
  }

  #text--lone {
    grid-column-start: 2;
    grid-column-end: 6;
    display: flex;
    justify-content: center;
    align-items: center;
    @media (min-width: 800px) {
      grid-column-start: 3;
      grid-column-end: 6
    }
    .quote {
      position: relative;
      display: inline-block;
      width: auto;
      p {
        font-family: Raleway;
        font-style: normal;
        font-weight: 900;
        //font-size: 38px;
        font-size: calc(22px + (38 - 22) * ((100vw - 300px) / (1600 - 300)));
        line-height: 94.9%;
        letter-spacing: -0.03em;
        color: #78b2bd;
        max-width: 500px;
      }
      #t1 {
        top: 0;
        left: 0;
      }
      #t2 {
        bottom: 0;
        right: 0;
      }
      .thick {
        position: absolute;
        font-family: Raleway;
        font-style: normal;
        font-weight: bold;
        font-size: 250px;
        color: white;
        opacity: 0.1;
        line-height: 0;
      }
    }
  }

</style>
