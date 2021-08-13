<template>
  <div class="ext-card">
    <div class="ext-card__icon">
      <img :src="ext.icon" alt="" aria-hidden="true" />
    </div>
    <h3 class="ext-card__title">Add to {{ ext.browser }}</h3>
    <p class="ext-card__subtitle">Minimum version {{ ext.min_version }}</p>
    <div class="ext-card__btn-wrapper">
      <BaseButton :width="230" :height="49">Add & Install Extension</BaseButton>
    </div>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
  props: {
    ext: {
      type: Object,
      required: true,
      // validator: card => card.hasOwnProperty("browser") && card.hasOwnProperty("version")
    }
  },
  components: {
    BaseButton,
  },
}
</script>

<style lang="scss">
.ext-card__btn-wrapper {
  border-image: url("../assets/images/bg-dots.svg") 27 space;
  border-top: 5px solid gray;

  border-top-image:
      url("../assets/images/bg-dots.svg")
      55 /
      5px / 
      0
      round;
      border-image-repeat: space;

}
</style>