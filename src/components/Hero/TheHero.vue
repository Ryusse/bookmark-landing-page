<template>
  <section class="hero" ref="root">
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
import { ref, toRefs } from "@vue/reactivity";
import BaseButton from "../Base/BaseButton.vue";
import { onMounted, onUnmounted } from "@vue/runtime-core";

export default {
  name: "TheHero",
  components: { BaseButton },
  props: { options: Object },

  setup(props, { emit }) {
    const observer = ref(null);
    const root = ref(null);
    const { options } = toRefs(props);

    const ioCallback = (entries) =>
      entries.forEach(({ isIntersecting, intersectionRatio }) =>
        emit("intersect", isIntersecting, intersectionRatio)
      );

    onMounted(() => {
      observer.value = new IntersectionObserver(ioCallback, options);
      observer.value.observe(root.value);
    });

    onUnmounted(() => {
      observer.value.disconnect();
    });

    return { observer, ioCallback, root };
  },
};
</script>
