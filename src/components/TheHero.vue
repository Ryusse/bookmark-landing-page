<template>
  <div>
    <BaseButton>Get it on Chrome</BaseButton>
    <BaseButton color="black" bgColor="#eee">Get it on Firefox</BaseButton>
  </div>
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

<style module lang="scss"></style>
