<template>
  <div class="section">
    <div class="gradient"></div>
    <video autoplay muted loop id="back--video">
        <source src="../../assets/videos/intro.mp4" type="video/mp4">
    </video>
    <div id="intro" class="animated fadeIn">
      <div class="main--slogan">
        <h1>Transformando el proceso y desarrollo de productos </h1>
        <h3>con soluciones integradas de alto rendimiento para el <br> diseño, simulación y fabricación.</h3>
      </div>
      <a class="goto-link" href="#" v-scroll-to="'#blog-widget'">
        <svg version="1.1" id="Layer_1" class="arrow-down" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
        	 viewBox="0 0 108.1 65.1" style="enable-background:new 0 0 108.1 65.1;" xml:space="preserve">
        <style type="text/css">
        	.st0{fill:#FFF;}
        </style>
        <polygon class="st0" points="107.5,12 95.5,0 53.7,41.7 12,0 0,12 53.7,65.8 "/>
        </svg>
      </a>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>

.section {
  display: flex;
  position: relative;
  width: 100%;
  height: 100vh;
  margin: 0;
  overflow: hidden;
}

#intro {
  // height: 100vh;
  // width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  // position: relative;
  //left: 0px;
  //top: 0px;
  position: relative;
  height: 80%;
  z-index: 5;
  h1 {
    margin-left: 5%;
    margin-right: 5%;
    transition: 0.5s;
    color: white;
    font-size: calc(25px + (60 - 25) * ((100vw - 300px) / (1600 - 300)));
    @media (min-height: 500px) {
      margin-left: 0;
      margin-right: 0;
    }
  }
  h3 {
    margin-left: 2.5%;
    margin-right: 2.5%;
    font-style: normal;
    font-weight: bold;
    transition: 0.5s;
    color: white;
    font-size: calc(11px + (20 - 11) * ((100vw - 300px) / (1600 - 300)));
    line-height: 1.2;
  }
}

.main--slogan {
  margin-left: 5%;
  margin-right: 5%;
  max-width: 800px;
  @media (min-height: 500px) {
    margin-left: 0;
    margin-right: 0;
  }
}

.goto-link {
  display: block;
  position: absolute;
  bottom: 0;
  width: 50px;
  @media (min-width: 400px) {
    width: 100px;
  }
}

.arrow-down {
  transition: 0.5s;
  width: 30px;
  @media (min-width: 400px) {
    width: 45px;
  }
  .st0 {
    transition: 0.5s;
    &:hover {
      fill: black;
    }
  }
}

.video {
    height: 100vh;
    width: 100%;
    position: absolute;
    left: 0px;
    top: 0px;
    z-index: -2;
    object-fit: cover;
}

#back--video {
  position: absolute;
  right: 0;
  bottom: 0;
  min-width: 100%;
  min-height: 100%;
  z-index: -2;
}

.gradient {
height: 100vh;
width: 100%;
position: absolute;
left: 0px;
top: 0px;
z-index: 3;
//background: linear-gradient(104.98deg, rgba(101, 163, 117, 0.6) 20.58%, rgba(196, 196, 196, 0.35) 100%);
background: linear-gradient(104.98deg, rgba(0, 0, 0, 0.5) 20.58%, rgba(0, 0, 0, 0.5) 100%);
}

// background: linear-gradient(to right,rgba(80,190,190,0.7) 0,rgba(0,153,153,0.7) 50%,rgba(0,153,176,0.7) 83%,rgba(0,153,203,0.7) 100%);

</style>
