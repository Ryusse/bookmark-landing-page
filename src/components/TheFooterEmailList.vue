<template>
  <section class="email-list">
    <span class="email-list__subtitle">35,000+ already joined</span>
    <h2 class="email-list__title">Stay up-to-date with what we’re doing</h2>
    <template v-if="!subscribed">
      <form
        class="email-list__signup"
        @submit.prevent="validateEmail"
        @keyup.enter="validateEmail"
        :class="{ invalid: !isEmailValid }"
      >
        <div class="input-wrapper">
          <input
            type="email"
            name="emailList"
            class="email-list__signup__email"
            placeholder="Enter your email address"
            v-model="userEnteredEmail"
            required
          />
          <transition name="email-alert-transition">
            <span class="email-list__signup__alert" v-if="!isEmailValid">
              Whoops, make sure it's an email
            </span>
          </transition>
        </div>
        <BaseButton
          :bgColor="'hsl(0, 94%, 66%)'"
          :width="125"
          :height="46"
          class="email-list__signup__btn"
        >
          Contact Us
        </BaseButton>
      </form>
    </template>
    <h3 v-else class="email-list__thank-note">Thanks for subscribing!</h3>
  </section>
</template>

<script>
import BaseButton from "./BaseButton.vue";

export default {
  name: "EmailList",
  components: {
    BaseButton,
  },
  data() {
    return {
      userEnteredEmail: "",
      isEmailValid: true,
      subscribed: false,
    };
  },
  methods: {
    validateEmail() {
      const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      const isValid = pattern.test(String(this.userEnteredEmail).toLowerCase());
      this.isEmailValid = isValid;
      this.subscribed = isValid;
    },
  },
};
</script>

<style lang="scss">
.invalid .input-wrapper::after {
  content: url("../assets/images/icon-error.svg");
  position: absolute;
  right: 10px;
  transform: translateY(50%);
}
</style>
