<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <img alt="Profitroles logo" class="logo" src="@/assets/logo.svg" />
    <nav>
      <RouterLink to="/">Découvrir</RouterLink>
      <RouterLink to="/events">Nos représentations</RouterLink>
    </nav>
  </header>
  <RouterView class="router-view" />
  <footer class="footer">
    <a href="https://www.facebook.com/leo.profitroles.9">Facebook</a>
    <a href="https://instagram.com/profit.roles?igshid=YmMyMTA2M2Y="
      >Instagram</a
    >
    <a href="mailto:profitroles.utc@gmail.com">Nous écrire</a>
  </footer>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 140px;
  width: 140px;
}

nav {
  font-size: 30px;
  text-align: center;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  font-weight: 500;
  line-height: 1em;
}

.footer {
  display: flex;
  justify-content: center;
  gap: 1em;
  align-items: center;
  text-align: center;
  line-height: 1.2em;
  height: 3em;
}

.footer a {
  opacity: 0.8;
}

.footer a:hover {
  opacity: 1;
}

@media (max-width: 534px) {
  header {
    flex-direction: column;
  }

  .logo {
    margin: -0.5em;
  }
}

@media (min-width: 1024px) {
  .logo {
    margin-right: 1em;
  }
}

@media (hover: hover) and (min-width: 534px) {
  nav a:hover {
    transform: translateY(-0.2em);
  }
}

@media (hover: hover) {
  nav a:hover {
    color: rgb(231, 185, 185);
  }
}
</style>