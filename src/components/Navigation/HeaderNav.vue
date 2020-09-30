<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({})
export default class HeaderNav extends Vue {}
</script>

<template>
  <div id="header-nav">
    <div class="container-nav">
      <div class="logo">SHIP-OVERVIEW</div>
      <nav class="nav">
        <router-link class="nav--link" to="/">Overview</router-link>
        <router-link class="nav--link" to="/about">About</router-link>
      </nav>
    </div>
  </div>
</template>

<style scoped lang="scss">
#header-nav {
  background: var(--main-bg);
  position: absolute;
  top: 0;
  right: 0;
  left: 0;
}

.container-nav {
  padding: 1rem;
  max-width: 1200px;
  margin: 0 auto;

  display: flex;
  justify-content: space-between;
}

.logo {
  font-size: 1.5rem;
  font-family: var(--logo-font);
  font-weight: 900;
  color: var(--white);
}
.nav {
  color: var(--light-color);

  display: flex;
  justify-content: space-between;
}
.nav--link {
  color: var(--white);
  text-decoration: none;
  display: block;
  padding: 0.5rem 1rem;
  transition: color 0.3s ease-in-out;
}
.nav--link:hover {
  color: var(--light-color);
}
</style>
