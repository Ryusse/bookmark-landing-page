<template>
  <main class="layout"> 
    <TheHeader />
    <TheHero />
    <TheFeatures/>
    <TheExtension />
    <TheFaq />
  </main>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheHero from "./components/TheHero.vue";
import TheExtension from './components/TheExtension.vue';
import TheFeatures from "./components/TheFeatures.vue";
import TheFaq from "./components/TheFaq.vue"

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    TheExtension,
    TheFeatures,
    TheFaq
  },
};
</script>

<style lang="scss">
@use './assets/sass/main.scss';
</style>
