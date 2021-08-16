<template>
  <main class="layout"> 
    <TheHeader />
    <TheHero />
    <TheFeatures/>
    <TheExtension />
    <TheFaq />
    <TheFooter />
  </main>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheHero from "./components/TheHero.vue";
import TheExtension from './components/TheExtension.vue';
import TheFeatures from "./components/TheFeatures.vue";
import TheFaq from "./components/TheFaq.vue";
import TheFooter from "./components/TheFooter.vue";

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    TheExtension,
    TheFeatures,
    TheFaq,
    TheFooter
  },
};
</script>

<style lang="scss">
@use './assets/sass/main.scss';
</style>
