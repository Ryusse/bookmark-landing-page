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
          <BaseButton class="hero-chrome-btn">Get it on Chrome</BaseButton>
          <BaseButton
            color="hsl(229, 31%, 21%)"
            bgColor="hsl(180deg 9% 98%)"
            class="hero-firefox-btn"
          >
            Get it on Firefox
          </BaseButton>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import BaseButton from "../Base/BaseButton.vue";

export default {
  name: "TheHero",
  components: { BaseButton },
  props: { options: Object },

  data: () => ({ observer: null }),

  methods: {
    ioCallback(entries) {
      entries.forEach(({ isIntersecting, intersectionRatio }) => {
        this.$emit("intersect", isIntersecting, intersectionRatio);
      })
    }
  },

  mounted() {
    const options = this.options ?? {};
    this.observer = new IntersectionObserver(this.ioCallback, options);
    this.observer.observe(this.$el);
  },

  unmounted() {
    this.observer.disconnect();
  },
};
</script>
