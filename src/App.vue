<template>
  <div class="my-app">
    <div v-if="loggedIn">
      Jesteś zalogowany
      <br>
      <button @click="logOut()">Wyloguj</button>
    </div>
    <div v-else>
    <h1>Witaj w systemie do zapisów na zajęcia </h1>
      <LoginForm @login="(username) => logMeIn(username)" button-label="Wejdź"></LoginForm>
      <LoginForm @login="(username) => logMeIn(username)" button-label="Wleć"></LoginForm>
      <LoginForm @login="(username) => logMeIn(username)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></LoginForm>
    </div>
  </div>

</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {

  components: {LoginForm},

  data() {
    return {
      authenticatedUsername: '',
      password: ''
    };
  },
  methods: {
    logMeIn(username) {
      this.authenticatedUsername = username;
    },
    logOut(){
      this.authenticatedUsername='';
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
