<template>
  <main class="layout"> 
    <TheHeader />
    <TheHero />
    <TheExtension />
  </main>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheHero from "./components/TheHero.vue";
import TheExtension from './components/TheExtension.vue';

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    TheExtension,
  },
};
</script>

<style lang="scss">
@use './assets/sass/main.scss';
</style>
