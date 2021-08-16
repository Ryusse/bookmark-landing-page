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
import TheHeader from "./components/Header/TheHeader.vue";
import TheHero from "./components/Hero/TheHero.vue";
import TheExtension from './components/Extension/TheExtension.vue';
import TheFeatures from "./components/Features/TheFeatures.vue";
import TheFaq from "./components/Faq/TheFaq.vue";
import TheFooter from "./components/Footer/TheFooter.vue";

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
