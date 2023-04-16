<template>
  <div class="my-app">
    <div v-if="loggedIn">
      Jesteś zalogowany
      <br>
      <button @click="logOut()">Wyloguj</button>
    </div>
    <div v-else>
    <h1>Witaj w systemie do zapisów na zajęcia </h1>
    Zaloguj się emailem:
    <input type="email" v-model="email">
    <button @click="logMeIn()">Wchodzę</button>
    </div>
  </div>

</template>

<script>
import "milligram";

export default {
  data() {
    return {
      email: '',
      loggedIn: false,
      password: '',
      loggedOut: true
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logMeIn(){
      this.loggedIn=true;
    },
    logOut(){
      this.loggedIn=false;
      this.email='';
    }
  }

}

</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
