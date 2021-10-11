<template>
  <div class="container">
    <h1>Login</h1>
    <form @submit.prevent="efetuarLogin">
      <div class="form-group">
        <label for="email">E-mail</label>
        <input
          type="mail"
          id="email"
          class="form-control"
          v-model="usuario.email"
        />
      </div>
      <div class="form-group">
        <label for="senha">Senha</label>
        <input
          type="password"
          id="senha"
          class="form-control"
          v-model="usuario.senha"
        />
      </div>
      <button class="btn btn-primary btn-block">Login</button>
      <router-link :to="{ name: 'novo.usuario' }">
        Não possui um cadastro, cadastre-se aqui!
      </router-link>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      usuario: {},
    };
  },
  methods: {
    efetuarLogin() {
      this.$store.dispatch('efetuarLogin', this.usuario)
      .then(() => this.$router.push({name: 'gerentes'}))
    },
  },
};
</script>