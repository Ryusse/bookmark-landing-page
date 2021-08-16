<template>
  <section class="emailList">
    <span class="emailList__subtitle">35,000+ already joined</span>
    <h2 class="emailList__title">Stay up-to-date with what we’re doing</h2>
    <form class="emailList__signup">
      <input
        type="email"
        name="emailList"
        class="emailList__signup__email"
        placeholder="Enter your email address"
      />
      <BaseButton
        :bgColor="'hsl(0, 94%, 66%)'"
        :width="125"
        :height="46"
        class="emailList__signup__btn"
      >
        Contact Us
      </BaseButton>
    </form>
  </section>
</template>

<script>
import BaseButton from "./BaseButton.vue";

export default {
  name: "TheEmailList",
  components: {
    BaseButton,
  },
  emialRegex: /^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/,
  methods: {
    validateEmail(email) {
      const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return pattern.test(String(email).toLowerCase());
    },
  },
};
</script>
