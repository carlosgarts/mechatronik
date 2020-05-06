<template>
    <div class="carousel-wrapper">
      <client-only>
        <agile ref="carousel" :options="options">
          <div class="video-wrapper wrapper">
            <div class="screen">
              <div class="content">
                <h2>Aliados ante todo</h2>
                <p>Mechatronik es ingenieria, es tecnologia y es su aliado para cualquier proyecto o reto presente en su empresa,
                  estamos especializados en una variedad de servicios desde electricos hasta de manufacturacion de productos
                  relacionados a motion control.
                </p>
              <a class="link" href="#">Ver mas &#10095</a>
              </div>
            </div>
            <video autoplay muted loop id="back--video">
                <source src="../../assets/videos/intro.mp4" type="video/mp4">
            </video>
          </div>
          <div v-for="slide in slides" :key="i" class="img-wrapper wrapper">
            <div class="screen">
              <div class="content">
                <h2>{{slide.title}}</h2>
                <p>{{slide.description}}</p>
              <a class="link" href="#">Ver mas &#10095</a>
              </div>
            </div>
            <img src="https://blog.mechatronik-group.com/wp-content/uploads/2020/01/14-1.jpg" />
          </div>
        </agile>
        <!-- <button @click="$refs.carousel.goToNext()">My custom button</button>
        <button @click="$refs.carousel.goToNext()">My custom button</button> -->
      </client-only>
    </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      options: {
        infinite: true,
        slidesToShow: 1,
        dots: true,
        autoplay: false,
        mobileFirst: true,
        fade: true,
        autoplaySpeed: 10000
      },
      slides: [
        {
          title: "Solidez para el futuro", //Control sobre las variables del futuro
          description: "Mediante nuestros gearboxes, grippers, servos, couplings y demas componentes que ofrecemos, su proyecto de motion control queda blindado ante el futuro, con tecnologia tan fiable como la de Siemens, Neugart y mas, respaldados por el soporte e ingenieria de Mechatronik.",
          imagen: "https://blog.mechatronik-group.com/wp-content/uploads/2020/01/14-1.jpg"
        },
        {
          title: "Aliados ante todo",
          description: "Mechatronik es ingenieria, es tecnologia y es su aliado para cualquier proyecto o reto presente en su empresa, estamos especializados en una variedad de servicios desde electricos hasta de manufacturacion de productos relacionados a motion control.",
          imagen: "https://blog.mechatronik-group.com/wp-content/uploads/2020/01/14-1.jpg"
        },
        {
          title: "Blog",
          description: "Mechatronik es ingenieria, es tecnologia y es su aliado para cualquier proyecto o reto presente en su empresa, estamos especializados en una variedad de servicios desde electricos hasta de manufacturacion de productos relacionados a motion control.",
          imagen: "https://blog.mechatronik-group.com/wp-content/uploads/2020/01/14-1.jpg"
        },
        {
          title: "Soluciones",
          description: "Mechatronik es ingenieria, es tecnologia y es su aliado para cualquier proyecto o reto presente en su empresa, estamos especializados en una variedad de servicios desde electricos hasta de manufacturacion de productos relacionados a motion control.",
          imagen: "https://blog.mechatronik-group.com/wp-content/uploads/2020/01/14-1.jpg"
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.wrapper {
  position: relative;
}
.screen {
  position: absolute;
  display: flex;
  //background: rgba(black, 0.3);
  background: rgb(0,85,120);
  background: linear-gradient(0deg, rgba(0,85,120,0.3) 0%, rgba(0,37,52,0.3) 50%, rgba(0,0,0,0.3) 100%);
  height: 100%;
  width: 100%;
  top: 0;
  right: 0;
  justify-content: flex-start;
  align-items: center;
  .content {
    display: block;
    max-width: 550px;
    width: 90%;
    height: auto;
    background: rgb(0,85,120);
    background: linear-gradient(90deg, rgba(0,85,120,0.7) 0%, rgba(101,163,174,0.7) 100%);
    text-align: left;
    color: white;
    padding: 35px 35px;
    margin-left: 5%;
    margin-top: 5%;
    @media (min-width: 600px) {
      width: 80%;
      margin-left: 10%;
    }
    h2 {
      font-size: 50px;
      margin-top: 0;
      font-weight: lighter;
    }
    p {
      margin: 0;
      line-height: 1.5;
      margin-bottom: 15px;
    }
    .link {
      display: block;
      width: 105px;
      transition: 0.5s;
      background-color: transparent;
      color: #ffb900;
      text-decoration: none;
      border: 1px solid #ffb900;
      padding: 9px 14px;
      margin-top: 15px;
      &:hover {
        background-color: #ffb900;
        color: rgb(0,85,120);
      }
    }
  }
}

.carousel-wrapper {
  height: 100vh;
  width: 100%;
}
.img-wrapper {
  text-align: center;
  img {
    margin: auto;
    width: 100%;
    height: 100vh;
    object-fit: cover;
    background-image: linear-gradient(gray 100%, transparent 0);
  }
}

.video-wrapper {
  width: 100%;
  height: 100vh;
}

#back--video {
  right: 0;
  bottom: 0;
  min-width: 100%;
  min-height: 100%;
  z-index: -2;
}

.agile__nav-button  {
  display: none;
}

//Vue Agile Styles

// VueAgile styles
.agile {
  &__dots {
    bottom: 10px;
    flex-direction: column;
    right: 30px;
    position: absolute;
  }
  &__dot {
    margin: 5px 0;

    button {
      background-color: transparent;
      border: 1px solid #fff;
      cursor: pointer;
      display: block;
      height: 15px;
      font-size: 0;
      line-height: 0;
      margin: 0;
      padding: 0;
      transition-duration: .3s;
      width: 15px;
    }

    &--current,
    &:hover {
      button {
          background-color: #fff;
      }
    }
  }
}
</style>
