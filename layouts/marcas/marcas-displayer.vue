<template>
  <div>
    <div class="product--searcher">
      <!-- <img class="big-arrow" src="../../assets/svg/great-arrow.svg" alt="arrow down"> -->
      <div class="product--list">
        <div class="list--content">
          <!-- <h2 class="sub-h2">Catálogo</h2> -->
          <!-- <slot name="name"> -->
          <div class="listas">
            <slot>

            </slot>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import loading from '../partials/loading.vue'

export default {
}
</script>

<style lang="scss" scoped>

.listas {
  margin-top: 25px;
}

.product--searcher {
  margin-top: 50px;
  width: 100vw;
  h2 {
    margin: 0;
    font-size: calc(35px + (45 - 35) * ((100vw - 300px) / (1600 - 300)));
    font-style: normal;
    font-weight: normal;
  }
  .sub-h2 {
    font-size: calc(30px + (40 - 35) * ((100vw - 300px) / (1600 - 300)));
  }
  h3 {
    font-size: 25px;
    font-style: normal;
    font-weight: normal;
    word-break: break-all;
    overflow: hidden;
  }
}

.category-selector {
  display: block;
  float: right;
  max-width: 50%;
  padding: 9px 9px;
  border: none;
  border: 2px solid #65A3AE;
  color: #65A3AE;
  background-color: transparent;
  -moz-appearance:none; /* Firefox */
    -webkit-appearance:none; /* Safari and Chrome */
    appearance:none;
    & .right {

    }
}

.product--header {
  display:flex;
  justify-content: center;
  width: 100%;
  background-color: #F3F3F3;
  position: relative;
  z-index: 2;
  .header--content {
    width: 90%;
    margin: 45px 0;
    max-width: 1200px;
    @media (min-width: 900px) {
      width: 80%;
    }
    p {
      max-width: 800px;
      line-height: 1.4;
      margin: 30px 0;
    }
    .nav-history {
      margin: 0;
    }
  }
}
.big-arrow {
  width: 100%;
  margin: 0;
  position: relative;
  top: -1px;
  z-index: 1;
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
}
.product--list {
  display: flex;
  width: 100%;
  justify-content: center;
  .list--content {
    display: grid;
    width: 90%;
    max-width: 1200px;
    position: relative;
    margin-bottom: 10%;
    @media (min-width: 900px) {
      width: 80%;
    }
  }
}

.lister {
  display: grid;
  grid-template-columns: 1fr;
  width: 100%;
  grid-column-gap: 15px;
  grid-row-gap: 15px;
  min-height: 300px;
  margin: 30px 0;
  @media (min-width: 600px) {
    grid-template-columns: 1fr 1fr;
  }
  @media (min-width: 900px) {
    grid-template-columns: 1fr 1fr 1fr;
  }
  @media (min-width: 1320px) {
    grid-template-columns: 1fr 1fr 1fr 1fr;
  }
}

.prod-card {
  position: relative;
  width: 100%;
  height: 100%;
  text-decoration: none;
  .card-content {
    transition: transform .5s;
    position: relative;
    width: 100%;
    height: 100%;
    padding: 25px;
    background-color: white;
    border: 1px solid #CCCCCC;
    color: black;
    h3 {
      text-align: left;
      color: #65A3AE;
    }
    h4 {
      text-align: left;
      margin: 10px 0;
      font-weight: 500;
      font-size: 14px;
      line-height: 1.3;
      color: #87888a;
    }
    img {
      width: 100%;
      height: 200px;
      object-fit: contain;
    }
    p {
      word-break: break-all;
      height: 55px;
      overflow:hidden;
      margin-top: 10px;
      margin-bottom: 30px;
      -webkit-mask-image: -webkit-gradient(linear, left top, left bottom, from(rgba(0,0,0,1)), to(rgba(0,0,0,0)));
      mask-image: gradient(linear, left top, left bottom, from(rgba(0,0,0,1)), to(rgba(0,0,0,0)));
    }
    .card-description {
      display: none;
      word-break: break-all;
      font-size: 12px;
      line-height: 2;
      p {
        ul {
          padding: 0;
        }
      }
    }
  }
}

.prod-card:hover {
  .card-content {
    transform: scaleX(105%) scaleY(105%);
    position: absolute;
    height: auto;
    z-index: 5;
  }
  .card-description {
    display: block;
  }
}

.buttom-link {
  transition: 0.5s;
  text-decoration: none;
  color: white;
  background-color: white;
  color: #65A3AE;
  padding: 7px 15px;
  display: block;
  width: 143px;
  border-radius: 18px;
  -webkit-box-shadow: 2px 6px 8px 1px rgba(140,140,140,0.4);
  -moz-box-shadow: 2px 6px 8px 1px rgba(140,140,140,0.4);
  box-shadow: 2px 6px 8px 1px rgba(140,140,140,0.4);
  &:hover {
    background-color: #65A3AE;
    color: white;
  }
}

.changers{
  padding: 20px;
  font-size: 50px;
  text-align: center;
  a {
    cursor: pointer;
    :hover {
      color: #65A3AE;
    }
    :disabled {
      color: gray;
    }
  }
  .unactive {
    display: none;
  }
}

.searcher {
  background-color: #F3F3F3;
  //border: 1px solid #CCCCCC;
  border: none;
  border-bottom: 2px solid #65A3AE;
  padding: 9px;
}

.searcher--btn {
  transition: 0.5s;
  color: #65A3AE;
  background-color: white;
  border: 1px solid #CCCCCC;
  padding: 9px;
  cursor: pointer;
}
.searcher--btn:hover {
  color: white;
  background-color: #65A3AE;
  border: 1px solid #CCCCCC;
  padding: 9px;
}

//Widget Category

.product-displayer {
  display: grid;
  width: 100%;
  grid-template-columns: 1fr;
  grid-column-gap: 25px;
  margin-top: 25px;
  // @media (min-width: 800px) {
  //   grid-template-columns: 1fr 1fr;
  // }
  .category-text {
    display: flex;
    flex-wrap: wrap;
    flex-flow: column;
    justify-content: center;
  }
  .category-cover {
    position: relative;
    width: 100%;
    max-height: 400px;
    grid-row: 1 / 2;
    img {
      width: 100%;
      height: 100%;
      position: static;
      object-fit: contain;
      @media (min-width: 800px) {
        //height: auto;
        position: relative;
        //top: 20px;
        object-fit: contain;
      }
    }
  }
}

</style>
