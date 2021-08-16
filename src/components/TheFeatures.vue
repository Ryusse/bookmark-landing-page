<template>
  <section class="features">
    <div class="features__container">
      <h2 class="features__title">Features</h2>
      <p class="features__text">
        Our aim is to make it quick and easy for you to access your favourite
        websites. Your bookmarks sync between your devices so you can access
        them on the go.
      </p>
    </div>

    <Tabs/>
  </section>
</template>

<script>
import Tabs from "./TheFeaturesTabs.vue";

export default {
  name: "TheFeatures",
  components: { Tabs },
};
</script>
