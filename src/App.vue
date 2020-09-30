<script lang="ts">
import { Options, Vue } from "vue-class-component";
import HeaderNav from "@/components/Navigation/HeaderNav.vue";

@Options({
  components: { HeaderNav }
})
export default class App extends Vue {}
</script>

<template>
  <HeaderNav />
  <router-view />
</template>

<style lang="scss">
:root {
  --font-family: Avenir, Helvetica, Arial, sans-serif;
  --main-bg: #1a1c48;
  --light-color: #9499c3;
  --white: rgb(221, 221, 221);
  --success: rgb(1, 109, 91);
  --warning: rgb(204, 127, 40);
  --logo-font: "Oswald", sans-serif;
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  font-family: var(--font-family);
  text-align: center;
  color: #2c3e50;
}
</style>
