<template>
  <section class="hero">
    <div class="wrapper">
      <div class="hero__col hero__col--1">
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
      <div class="hero__col hero__col--2"></div>
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

<style lang="scss">
@use '../assets/sass/abstracts/all' as *;

.wrapper {
  flex: 1;
  min-height: calc(100vh - 158px);
  @include flexbox(column-reverse);
  @include query(md) {
    @include flexbox(row, null, center);
    > * { flex:1 1 100% }
  }
}

.hero__col--1 {
  @include flexbox(col, null, center);
  text-align: center;
  @include query(md) {
    text-align: left;
    @include flexbox(col, null, flex-start);
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
  @include font-size($p-font-sizes);
  color: $grayish-blue;
  line-height: 1.5;
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

.hero__col--2 {
  position: relative;
  background-color: coral;
  background: url("../assets/images/illustration-hero.svg") no-repeat center;
  background-size: contain;
  height: max(350px, 50vw);
  background-size: max(330px, 70vw);
  @include query(md) {
    background-size: contain;
  }

  // &::before {
  //   content: "";
  //   position: absolute;
  //   height: 50%;
  //   width: 80%;
  //   right: -10%;
  //   top: 50%;
  //   transform: translateY(-40%);
  //   background-color: $soft-blue;
  //   border-radius: 5000px 0 0 5000px;
  //   overflow: hidden;
  //   z-index: -1;
  // }

  &::before{
    position: absolute;
    content: "";
    top: clamp(64px, 15vw, 90px);
    left: 21vw;
    width: 100vw;
    height: 54vw;
    max-height: 324px;
    background-color: $soft-blue;
    z-index: -1;
  }
}
</style>
