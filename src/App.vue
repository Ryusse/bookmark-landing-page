<template>
  <main class="layout"> 
    <TheHeader />
    <TheHero />
    <TheExtensions />
  </main>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheHero from "./components/TheHero.vue";
import TheExtensions from './components/TheExtensions.vue';

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    TheExtensions,
  },
};
</script>

<style lang="scss">
@use './assets/sass/main.scss';
</style>
