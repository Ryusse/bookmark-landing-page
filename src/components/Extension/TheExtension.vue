<template>
  <section class="extensions primary-title-subtitle">
    <h2 class="extensions__title">Download the extension</h2>
    <p class="extensions__content">We’ve got more browsers in the pipeline. Please do let us know if you’ve got a favourite you’d like us to prioritize.</p>
    <div class="extensions__card-wrapper">
      <ExtensionCard v-for="(ext, i) in cardData" :key="i" :ext="ext" />
    </div>
  </section>
</template>

<script>
import ExtensionCard from './TheExtensionCard.vue';

import IconChrome from '../../assets/images/logo-chrome.svg';
import IconFirefox from '../../assets/images/logo-firefox.svg';
import IconOpera from '../../assets/images/logo-opera.svg';

export default {
  name: "TheExtension",
  components: {
    ExtensionCard
  },
  data() {
    return {
      cardData: [
        {
          icon: IconChrome,
          browser: "Chrome",
          min_version: "62"
        },
        {
          icon: IconFirefox,
          browser: "Firefox",
          min_version: "55"
        },
        {
          icon: IconOpera,
          browser: "Opera",
          min_version: "46"
        },
      ]
    }
  },
};
</script>
