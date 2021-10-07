<template>
  <div class="container">
    <h1>Cadastro de Usuário</h1>
    <form @submit.prevent="enviarFormulario">
      <div class="form-group">
        <label for="nome">Nome</label>
        <input
          type="text"
          id="nome"
          class="form-control"
          v-model="usuario.nome"
        />
      </div>
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
      <button class="btn btn-primary">Salvar</button>
    </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      usuario: {
        nome: "",
        senha: "",
        email: "",
      },
    };
  },
  methods: {
    enviarFormulario() {
      console.log(this.usuario);
      axios
        .post("http://localhost:8000/auth/register", this.usuario)
        .then((resposta) => console.log(resposta))
        .catch((erro) => console.log(erro));
    },
  },
};
</script>