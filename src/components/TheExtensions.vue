<template>
  <section class="extensions">
    <h1 class="extensions__title">Download the extension</h1>
    <p class="extensions__content">We’ve got more browsers in the pipeline. Please do let us know if you’ve got a favourite you’d like us to prioritize.</p>
    <div class="extensions__card-wrapper">
      <ExtensionCard v-for="ext in cardData" :key="ext.id" :ext="ext" />
    </div>
  </section>
</template>

<script>
import ExtensionCard from './ExtensionsCard.vue';

import IconChrome from '../assets/images/logo-chrome.svg';
import IconFirefox from '../assets/images/logo-firefox.svg';
import IconOpera from '../assets/images/logo-opera.svg';

export default {
  name: "TheExtensions",
  components: {
    ExtensionCard
  },
  data() {
    return {
      cardData: [
        {
          id: 1,
          icon: IconChrome,
          browser: "Chrome",
          min_version: "62"
        },
        {
          id: 2,
          icon: IconFirefox,
          browser: "Firefox",
          min_version: "55"
        },
        {
          id: 3,
          icon: IconOpera,
          browser: "Opera",
          min_version: "46"
        },
      ]
    }
  },
};
</script>
