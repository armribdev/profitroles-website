<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <img
      alt="Profitroles logo"
      class="logo"
      src="@/assets/logo.svg"
      width="125"
      height="125"
    />
    <nav>
      <RouterLink to="/">Découvrir</RouterLink>
      <RouterLink to="/events">Nos représentations</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

nav {
  font-size: 24px;
  text-align: center;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
}

@media (min-width: 1024px) {
  .logo {
    margin-right: 1em;
  }
}
</style>
