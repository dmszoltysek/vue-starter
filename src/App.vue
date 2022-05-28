<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>

    <div v-if="authenticatedUsername == ''">
<!--      <login-form @login="logMeIn($event)"></login-form>-->
      <login-form @login="logMeIn($event)" button-label="Wejdź"></login-form>
<!--      <login-form @login="logMeIn($event)" button-label="Wleć"></login-form>-->
<!--      <login-form @login="logMeIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>-->
    </div>
  <div v-else>
    <logout-form :email="authenticatedUsername"
    @logout="logOut()"></logout-form>
  </div>
  </div>
</template>


<script>
import "milligram";
import LoginForm  from "./LoginForm";
import LogoutForm from "./LogoutForm";
export default {
  components: {LoginForm, LogoutForm},
  data() {
    return {
      authenticatedUsername: '',
    };
  },
  methods: {
    logMeIn(username) {
      this.authenticatedUsername = username;
    },
    logOut() {
      this.authenticatedUsername = '';
    }
  }
}
</script>

<style>
</style>
