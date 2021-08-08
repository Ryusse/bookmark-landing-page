<template>
  <section class="hero">
    <div class="hero__col hero__col--1">
      <h1 class="hero__col__title">A Simple Bookmark Manager</h1>
      <p class="hero__col__desc">
        A clean and simple interface to organize your favourite websites.
        Open a new browser tab and see your sites load instantly. Try it for free.
      </p>
      <div class="hero__col__btns">
        <BaseButton>Get it on Chrome</BaseButton>
        <BaseButton color="black" bgColor="#eee">Get it on Firefox</BaseButton>
      </div>
    </div>
    <div class="hero__col hero__col--2"></div>
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

<style scoped lang="scss">
@use '../assets/sass/abstracts/all' as *;

.hero {
  @include flexbox(column-reverse);
  min-height: calc(100vh - 100px);

  @include query(md) {
    @include flexbox(row);
  }

  > * {
    flex-basis: 100%;
  }
}

.hero__col {
  &--1 {
    background-color: powderblue;
  }
  &--2 {
    background: url("../assets/images/illustration-hero.svg") no-repeat;
    background-size: contain;
    background-color: coral;
    width: 100%;
    height: auto;
  }
}

.hero__col__btns {
  @include flexbox;
}

</style>
