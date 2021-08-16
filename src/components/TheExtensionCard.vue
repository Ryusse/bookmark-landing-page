<template>
  <div class="ext-card">
    <div class="ext-card__icon">
      <img :src="ext.icon" alt="" aria-hidden="true" width="105" height="100" />
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
      validator: card =>
        "browser" in card && "min_version" in card && (typeof card.icon === "string")
    }
  },
  components: {
    BaseButton,
  },
}
</script>
