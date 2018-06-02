<template>
  <form class="form-signin" v-on:submit.prevent="onSubmit">
      <div class="text-center mb-4">
        <h1 class="h3 mb-3 font-weight-normal">Entrar no Sistema</h1>
      </div>

      <div class="form-label-group">
        <input v-model="login" id="inputEmail" class="form-control" placeholder="Email address" required autofocus>
        <label for="inputEmail">Login</label>
      </div>

      <div class="form-label-group">
        <input v-model="senha" type="password" id="inputPassword" class="form-control" placeholder="Password" required>
        <label for="inputPassword">Password</label>
      </div>

      <div v-if="false" class="checkbox mb-3">
        <label>
          <input type="checkbox" value="remember-me"> Remember me
        </label>
      </div>
      <button @click="onLoginEvent" class="btn btn-lg btn-info btn-block" type="submit">Entrar</button>
      <p class="mt-5 mb-3 text-muted text-center">© 2018</p>
    </form>
</template>

<script>
export default {
  name: "HelloWord",
  methods: {
    onLoginEvent() {
      sessionStorage.setItem('token-this-application', 'token');
      this.$emit("on-login");
    }
  },
  props: {
    login: "",
    senha: ""
  },
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
:root {
  --input-padding-x: 0.75rem;
  --input-padding-y: 0.75rem;
}

html,
body {
  height: 100%;
}

body {
  display: -ms-flexbox;
  display: flex;
  -ms-flex-align: center;
  align-items: center;
  padding-top: 40px;
  padding-bottom: 40px;
  background-color: #f5f5f5;
}

.form-signin {
  width: 100%;
  max-width: 420px;
  padding: 15px;
  margin: auto;
}

.form-label-group {
  position: relative;
  margin-bottom: 1rem;
}

.form-label-group > input,
.form-label-group > label {
  padding: var(--input-padding-y) var(--input-padding-x);
}

.form-label-group > label {
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  width: 100%;
  margin-bottom: 0; /* Override default `<label>` margin */
  line-height: 1.5;
  color: #495057;
  border: 1px solid transparent;
  border-radius: 0.25rem;
  transition: all 0.1s ease-in-out;
}

.form-label-group input::-webkit-input-placeholder {
  color: transparent;
}

.form-label-group input:-ms-input-placeholder {
  color: transparent;
}

.form-label-group input::-ms-input-placeholder {
  color: transparent;
}

.form-label-group input::-moz-placeholder {
  color: transparent;
}

.form-label-group input::placeholder {
  color: transparent;
}

.form-label-group input:not(:placeholder-shown) {
  padding-top: calc(var(--input-padding-y) + var(--input-padding-y) * (2 / 3));
  padding-bottom: calc(var(--input-padding-y) / 3);
}

.form-label-group input:not(:placeholder-shown) ~ label {
  padding-top: calc(var(--input-padding-y) / 3);
  padding-bottom: calc(var(--input-padding-y) / 3);
  font-size: 12px;
  color: #777;
}
</style>
