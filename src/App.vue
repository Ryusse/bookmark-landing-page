<template>
  <main class="layout">
    <TheHeader ref="header" />
    <TheHero @intersect="intersected" :options="observerOptions"  />
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
  data() {
    return {
      frames: 100,
    };
  },
  computed: {
    observerOptions() {
      const thresholdArray = Array.apply(null, { length: this.frames }).map(
        (x, i) => i / this.frames
      );
      return {
        threshold: thresholdArray,
      };
    },
  },
  methods: {
    intersected(isIntersecting, intersectionRatio) {
      const translate =
        (Math.round(intersectionRatio * this.frames) / this.frames) * 100;
      const header = this.$refs.header.$el;

      if (!isIntersecting) {
        header.style.position = "sticky";
        header.style.transform = `translateY(-${translate}%)`;
      } else {
        header.style.transform = 'translateY(0%)';
        console.log(`translateY(-${translate}%)`);
        header.style.position = "relative";
      }
    },
  },
};
</script>

<style lang="scss">
@use './assets/sass/main.scss';
</style>
