<template>
  <div id="app">
    <Login v-if="!logado" v-on:on-login="onLogin" :login="user.login" />
  </div>
</template>

<script>
import Login from "./components/Login";

export default {
  name: "App",
  data () {
    return {
      user: {
        login: "",
        senha:""
      },
      logado : false
    };
  },
  methods: {
    onLogin: function() {
      var token = sessionStorage.getItem('token-this-application');
      console.log('token = ' + token);

    }
  },
  components: {
    Login
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
