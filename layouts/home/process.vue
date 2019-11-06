<template>
  <div class="section">
    <div id="process">
      <h3>Our <strong>Expertise</strong></h3>
      <p class="subtitle">We offer add on services to compliment our products, supporting you at every step or bridging your resource gap, ensuring succes, on time, on specification, every time.</p>
      <div class="cards">
        <div id="card-1" class="card">
          <div class="tbb">
          <h2>Electrical <br> Services</h2>
          </div>
          <p class="text">
            We provide a single source solution for custom industrial control panels including design, assembly, and full quality acceptance testing
          </p>
        </div>
        <div id="card-2" class="card">
          <div class="tbb">
          <h2>Software <br> Services</h2>
          </div>
          <p class="text">
          Mechatronik-Lösungen take advantage of the latest programming tools including TIA portal and Simotion Scout.
          <br> <br>
          Software development is always tailored to the customer's needs. Our software is fully documented and we are able to provide handover training where required so that customers can support and develop their own machines long term.</p>
        </div>
        <div id="card-3" class="card">
          <div class="tbb">
          <h2>Mechanical <br> Services</h2>
          </div>
          <p class="text">
            In engineering design the technical knowledge and design expertise of the designer are both key, and can only come from years of experience.
          </p>
        </div>
        <div id="card-4" class="card">
          <div class="tbb">
          <h2>Motion <br> Control</h2>
          </div>
          <p class="text">
            When electric motors have especial requirements due to performance criteria, size or evironment that have not been designed for before, Mechatronik-Lösungen have the skills and expertise to supply custom motor solutions, working with customers through all phases from the design through to assembly and testing
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
  .section {
    background: #65A3AE;
    background-image: url('../../assets/images/Inicio/fondo-inicio.jpg');
    background-attachment: fixed;
    z-index: -10;
    align-items: flex-start;
  }
  #process {
    display: block;
    width: 100%;
    @media (min-width: 1000px) {
      height: 120vh;
    }
    @media (min-width: 1100px) {
      height: 700px;
    }
    h3 {
      color: white;
      text-align: left;
      font-family: Raleway;
      font-style: normal;
      font-weight: normal;
      font-size: calc(35px + (55 - 35) * ((100vw - 300px) / (1600 - 300)));
      margin: 60px;
      margin-bottom: 20px;
    }
    .subtitle {
      color: white;
      text-align: left;
      font-family: Raleway;
      font-style: normal;
      font-weight: normal;
      text-shadow: 1px 1px 1px black;
      font-size: 1em;
      line-height: 1.3;
      @media (min-width: 400px) {
        font-size: 18px;
      }
      @media (min-width: 600px) {
        width: 80%;
        margin-left: 60px;
        margin-bottom: 60px;
      }
    }
    img {
      width: 100%;
    }
  }

  .cards {
    display: flex;
    color: white;
    width: 90%;
    justify-content: center;
    flex-wrap: wrap;
    margin-left: 5%;
    margin-right: 5%;
    margin-bottom: 100px;
    @media (min-width: 1000px) {
      justify-content: center;
      margin-bottom: 0;
      margin-left: 0;
      margin-right: 0;
      width: 100%;
    }
    @media (min-width: 1200px) {
      justify-content: center;
    }
    .card {
      transition: 0.5s;
      padding: 10px;
      padding-left: 20px;
      @media (min-width: 1000px) {
        min-width: 210px;
        width: 200px;
        height: 200px;
        margin-left: 20px;
        margin-right: 20px;
        padding: 10px;
      }
      @media (min-width: 1200px) {
        width: 280px;
        height: 400px;
      }
      .tbb {
        margin: 0;
        h2 {
          padding-bottom: 15px;
          font-size: 28px;
        }
      }
      &:hover .text{
        opacity: 1;
      }
      .text {
        transition: 0.5s ease-in;
        opacity: 1;
        overflow: hidden;
        text-align: justify;
        font-size: 14px;
        @media (min-width: 910px) {
          opacity: 0;
        }
      }
      h2 {
        text-align: left;
      }
    }
  }
</style>
