<template>
  <TheHeader />
  <TheHero />
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheHero from './components/TheHero.vue';

export default {
  name: 'App',
  components: {
    TheHeader,
    TheHero
  }
}
</script>

<style lang="scss">
@use './assets/sass/main.scss';
</style>
