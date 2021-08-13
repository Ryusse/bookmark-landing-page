<template>
  <main class="layout"> 
    <TheHeader />
    <TheHero />
    <TheFeatures/>
    
  </main>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheHero from "./components/TheHero.vue";
import TheFeatures from "./components/TheFeatures.vue";

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    TheFeatures,
  },
};
</script>

<style lang="scss">
@use './assets/sass/main.scss';
</style>
