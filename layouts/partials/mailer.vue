<template>
  <div class="mailer">
    <img class="show-img" src="@/assets/images/Inicio/newsletter.jpg" alt="mechatronik contactanos">
    <div class="content">
      <h4>GET<br>TO<br>KNOW<br>US<br>BETTER</h4>
      <div v-if="resultado == null">
        <div class="controller">
          <input class="email" type="email" name="email" v-model="interesado" placeholder="Enter your email" value="">
          <button class="sender" type="button" name="send" v-on:click="sendMail()"> <img class="send-img" src="@/assets/images/arrow-right.png" alt=" > "> </button>
        </div>
        <div class="advice">Enter your email address to get started.</div>
      </div>
      <div v-else>
        <div class="advice">{{resultado}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      interesado: '',
      resultado: null
    }
  },
  methods: {
    sendMail: async function() {
      if (this.interesado != '') {
        try {
          var consulta = 'https://system.mechatronik-group.com/api/mail/';
          consulta = consulta.concat(this.interesado);
          var Sender = await this.$axios.get(consulta);
          this.services = Sender.data.servicios;
          this.isLoading = false;
          if (Sender.data.result == '') {
            this.resultado = "Your mail has been sent, thanks, we'll get back to you soon";
          }
          else {
            this.resultado = "Something went wrong, try again later please."
          }
        } catch (e) {
          this.isLoading = false;
          console.log(e);
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .mailer {
    position: relative;
    width: 100%;
    height: 100%;
    display: grid;
    grid-template-columns: 100%;
    background-color: white;
    @media (min-width: 700px) {
      grid-template-columns: 40% 60%;
    }
    @media (min-width: 850px) {

    }
    .content {
      padding: 50px;
    }
    .show-img {
      position: absolute;
      opacity: 0.15;
      height: 100%;
      width: 100%;
      object-fit: cover;
      @media (min-width: 700px) {
        opacity: 1;
        position: relative;
        height: 100%;
      }
    }
    .controller {
      position: relative;
      display: flex;
      z-index: 20;
    }
    .email {
      height: 25px;
      width: 60%;
      background-color: #EEF6F8;
      border: none;
      color: rgba(0, 0, 0, 0.7);
      font-weight: bold;
      padding: 22px;
    }
    .sender {
      height: 45px;
      background-color: #EEF6F8;
      border: none;
      margin-left: 25px;
      cursor: pointer;
    }
    .send-img {
      height: 100%;
    }
    h4 {
      font-family: Raleway;
      font-style: normal;
      margin-bottom: 25px;
      margin-top: 25px;
      line-height: 0.8;
      font-size: 60px;
      color: #000;
      font-weight: bolder;
      text-align: left;
      @media (min-width: 400px) {
        font-size: 70px;
      }
    }
    .advice {
      margin: 8px;
    }
  }
</style>
