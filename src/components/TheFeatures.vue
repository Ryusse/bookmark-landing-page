<template>
  <div class="features">
    <div class="features-container">
      <h2 class="features-container__title">Features</h2>
      <p class="features-container__text">
        Our aim is to make it quick and easy for you to access your favourite
        websites. Your bookmarks sync between your devices so you can access
        them on the go.
      </p>

      <Switch/>
    </div>
  </div>
</template>

<script>
import Switch from './Switch.vue';
export default {
  name: "TheFeatures",
  components: {Switch}
};
</script>

<style scoped lang="scss">
</style>