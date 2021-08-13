<template>
  <div class="ext-card">
    <div class="ext-card__icon"> {{ ext.icon }} </div>
    <h3 class="ext-card__title">Add to {{ ext.browser }}</h3>
    <p class="ext-card__subtitle">Minimum version {{ ext.min_version }}</p>
    <div class="ext-card__btn-wrapper">
      <BaseButton>Add & Install Extension</BaseButton>
    </div>
    <p>
Add to Firefox
Minimum version 55


Add to Opera
Minimum version 46
Add & Install Extension
    </p>
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

<style>

</style>