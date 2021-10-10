<template>
  <ul class="navbar-nav mr-auto">
    <li class="nav-item">
      <router-link class="nav-link" to="/login">Login</router-link>
    </li>
    <li class="nav-item">
      <router-link to="/cadastre-se" class="nav-link">
        Registre-se
      </router-link>
    </li>
  </ul>
</template>

<script>
export default {
  methods: {
    efetuarLogout() {
      localStorage.removeItem("token");
      this.$router.push({ name: "login" });
    },
  },
};
</script>