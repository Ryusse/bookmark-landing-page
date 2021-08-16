<template>
  <section class="hero">
    <div class="wrapper">
      <div class="hero__col hero__col--illustration"></div>
      <div class="hero__col hero__col--content">
        <h1 class="hero__col__title">A Simple Bookmark Manager</h1>
        <p class="hero__col__desc">
          A clean and simple interface to organize your favourite websites. Open
          a new browser tab and see your sites load instantly. Try it for free.
        </p>
        <div class="hero__col__btns">
          <BaseButton>Get it on Chrome</BaseButton>
          <BaseButton
            color="hsl(229, 31%, 21%)"
            bgColor="hsl(180deg 9% 98%)"
            class="firefox-btn"
          >
            Get it on Firefox
          </BaseButton>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import BaseButton from "./BaseButton.vue";

export default {
  name: "TheHero",
  components: {
    BaseButton,
  },
};
</script>

<style lang="scss" scoped>

</style>
