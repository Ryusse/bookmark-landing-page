<template>
  <section class="hero">
    <div class="hero__col hero__col--1"></div>
    <div class="hero__col hero__col--2">
      <h1 class="hero__col__title">A Simple Bookmark Manager</h1>
      <p class="hero__col__desc">
        A clean and simple interface to organize your favourite websites. Open a
        new browser tab and see your sites load instantly. Try it for free.
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
  </section>
</template>

<script>
import BaseButton from "./BaseButton.vue";
import "../assets/images/illustration-hero.svg";

export default {
  name: "TheHero",
  components: {
    BaseButton,
  },
};
</script>

<style lang="scss">
@use '../assets/sass/abstracts/all' as *;

.hero {
  @include query(md) {
    @include flexbox(row-reverse);
  }
}

.hero__col--1 {
  position: relative;
  width: 100%;
  height: 64vw;
  isolation: isolate;
  margin-bottom: 2.6vw;
  // border: 1px solid #000;
  @include query(md) {
    height: auto;
  }

  &::before,
  &::after {
    content: "";
    position: absolute;
  }

  &::before {
    width: 85%;
    height: 84%;
    right: -2.58%;
    top: 20%;
    background-color: $soft-blue;
    border-radius: 5000px 0 0 5000px;
  }

  &::after {
    width: 100%;
    height: 100%;
    background: url("../assets/images/illustration-hero.svg") center no-repeat;
    background-size: 100%;
  }
}

.hero__col--2 {
  margin-top: 18vw;
  padding: 0 6vw;
  text-align: center;
  @include flexbox(col, null, center);
  @include query(md) {
    margin-top: 0;
    text-align: left;
  }
}

.hero__col__title {
  max-width: 380px;
  font-weight: 500;
  color: $very-dark-blue;
  @include font-size($h1-font-sizes);
  @include query(md) { max-width: none }
}

.hero__col__desc {
  max-width: 540px;
  margin-top: 20px;
  color: $grayish-blue;
  line-height: 1.5;
  @include font-size($p-font-sizes);
}

.hero__col__btns {
  width: 100%;
  margin-top: 30px;
  max-width: 380px;
  @include flexbox(null, space-between);
  @include query(md) { max-width: 345px }

  .firefox-btn > button {
    box-shadow: 0 5px 7px #00000020;
    margin-left: 5px;

    &:hover,
    &:focus {
      background-color: transparent !important;
      color: hsl(229, 31%, 21%) !important;
      border-color: hsl(229, 31%, 21%) !important;
    }

  }
}
</style>
