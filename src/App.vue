<template>
  <main class="layout"> 
    <TheHeader />
    <TheHero />
    <TheFeatures/>
    <TheExtension />
    
    
  </main>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheHero from "./components/TheHero.vue";
import TheFeatures from "./components/TheFeatures.vue";
import TheExtension from './components/TheExtension.vue';

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    TheFeatures,
    TheExtension,
  },
};
</script>

<style lang="scss">
@use './assets/sass/main.scss';
</style>
