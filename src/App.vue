<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <img alt="Profitroles logo" class="logo" src="@/assets/logo.svg" />
    <nav class="website-nav">
      <RouterLink to="/">Découvrir</RouterLink>
      <RouterLink to="/events">Nos représentations</RouterLink>
    </nav>
  </header>
  <RouterView class="router-view" />
  <footer class="footer">
    <nav class="external-links">
      <a href="https://www.facebook.com/leo.profitroles.9">Facebook</a>
      <a href="https://instagram.com/profit.roles?igshid=YmMyMTA2M2Y="
        >Instagram</a
      >
      <a href="mailto:profitroles.utc@gmail.com">Nous écrire</a>
    </nav>
    <div class="credits">
      <span>Crédits</span>
      <span>Illustrations : Julie Asselin</span>
      <span
        >Site : Armand Ribault
        <!-- ce bg enfaite --></span
      >
    </div>
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

.website-nav {
  font-size: 30px;
  text-align: center;
}

.website-nav a.router-link-exact-active {
  color: var(--color-text);
}

.website-nav a {
  display: inline-block;
  padding: 0 1rem;
  font-weight: 500;
  line-height: 1em;
}

.external-links {
  display: flex;
  justify-content: center;
  gap: 1em;
  align-items: center;
  text-align: center;
  line-height: 1.2em;
  height: 3em;
}

.external-links a {
  opacity: 0.8;
}

.external-links a:hover {
  opacity: 1;
}

.credits {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  font-size: 0.8em;
  opacity: 0.8;
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
  .website-nav a:hover {
    transform: translateY(-0.2em);
  }
}

@media (hover: hover) {
  .website-nav a:hover {
    color: rgb(231, 185, 185);
  }
}
</style>