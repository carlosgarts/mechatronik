<template>
  <div>
    <Navigation/>
    <nuxt />
    <mechafooter class="foot" />
  </div>
</template>

<script>
import Navigation from '~/layouts/partials/nav.vue'
import mechafooter from '~/layouts/partials/footer.vue'

export default {
  components: {
    Navigation,
    mechafooter
  }
}
</script>

<style lang="scss">
@import "../assets/css/animate.scss";
@import "../assets/css/fonts.css";


html {
  font-family: OpenSans, Roboto, Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

.tbb {
  border-bottom: 10px double white;
  border-width: thin;
  padding-left: 0;
  padding-right: 0;
  margin-left: 5%;
  margin-right: 5%;
  margin-bottom: 10px;
  @media (min-width: 600px) {
    margin-left: 10%;
  }
  h2 {
    font-family: Raleway;
    font-style: normal;
    font-weight: normal;
    font-size: 40px;
    line-height: 96.4%;
    color: #FFFFFF;
    text-align: left;
    border-bottom: 10px double white;
    border-width: thin;
    padding-bottom: 25px;
    margin-bottom: 12px;
  }
}

.section {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.short-section {
  min-height: 50vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.flex-section {
  display: flex;
  justify-content: center;
  align-items: center;
}
.side-tag {
  transform: rotate(270deg);
  transform-origin: center left;
  position: absolute;
  left: 0;
  bottom: 0;
  span {
    color: #65A3AE;
  }
}

.nav-history {
  a {
    color: #65A3AE;
    text-decoration: none;
  }
}

.error {
  display: flex;
  height: calc(100vh - 100px);
  margin-top: 100px;
  width: 100%;
  align-items: center;
  flex-flow: column;
  text-align: center;
  justify-content: center;
  background-color: white;
  .logo {
    width: 300px;
  }
}

//Loader

$grey: rgba(0, 0, 0, .5);
$blue: rgba(101, 163, 174, .5);

@keyframes rotate {
	0% {
		transform: rotate(0deg);
	}
	50% {
		transform: rotate(180deg);
	}
	100% {
		transform: rotate(360deg);
	}
}

@keyframes rotate2 {
	0% {
		transform: rotate(0deg);
		border-top-color: $grey;
	}
	50% {
		transform: rotate(180deg);
		border-top-color: $blue;
	}
	100% {
		transform: rotate(360deg);
		border-top-color: $grey;
	}
}

* {
	box-sizing: border-box;
}

h1, h3 {
	display: block;
	margin: 0px auto;
	text-align: center;
	font-family: 'Tahoma';
	font-weight: lighter;
	color: $grey;
	letter-spacing: 1.5px;
}

h1 {
	margin: 50px auto;
}

@mixin loaderDivMixin {
	border-radius: 50%;
	padding: 8px;
	border: 2px solid transparent;
	animation: rotate linear 3.5s infinite;
}

.loader {
	position: relative;
	margin: 75px auto;
	width: 150px;
	height: 150px;
	display: block;
	overflow: hidden;
	div {
		height: 100%;
	}
}

/* loader 1 */
.loader1, .loader1 div {
	@include loaderDivMixin;
	border-top-color: $grey;
	border-bottom-color: $blue;
}
div:hover {
	animation-play-state: paused;
}

.loader, .loader * {
	will-change: transform;
}
</style>
