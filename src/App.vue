<template>
  <main class="layout">
    <TheHeader ref="header" />
    <TheHero @intersect="intersected" :options="observerOptions" />
    <TheFeatures />
    <TheExtension />
    <TheFaq />
    <TheFooter />
  </main>
</template>

<script>
import TheHeader from "./components/Header/TheHeader.vue";
import TheHero from "./components/Hero/TheHero.vue";
import TheExtension from "./components/Extension/TheExtension.vue";
import TheFeatures from "./components/Features/TheFeatures.vue";
import TheFaq from "./components/Faq/TheFaq.vue";
import TheFooter from "./components/Footer/TheFooter.vue";
import { reactive } from "@vue/reactivity";

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    TheExtension,
    TheFeatures,
    TheFaq,
    TheFooter,
  },

  setup() {
    const observerOptions = reactive({ threshold: 0 });
    return { observerOptions };
  },

  methods: {
    intersected(isIntersecting) {
      const header = this.$refs.header.$el;

      if (!isIntersecting) header.style.position = "sticky";
      else header.style.position = "relative";
    },
  },
};
</script>

<style lang="scss">
@use './assets/sass/main.scss';
</style>
