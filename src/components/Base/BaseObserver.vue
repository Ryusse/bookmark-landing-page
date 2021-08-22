<template>
  <div class="observer" />
</template>

<script>
export default {
  props: {
    options: Object,
  },
  data() {
    return {
      observer: null,
    };
  },
  mounted() {
    const options = this.options ?? {};

    this.observer = new IntersectionObserver((entries) => {
      entries.forEach(({ isIntersecting, intersectionRatio }) => {
        this.$emit("intersect", isIntersecting, intersectionRatio);
      });
    }, options);

    this.observer.observe(this.$el);
  },
  unmounted() {
    this.observer.disconnect();
  },
};
</script>

<style lang="scss" scoped>
  .observer {
    height: 200px;
    width: 0.2px;
    opacity: 0;
  }
</style>