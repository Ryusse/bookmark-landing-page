<template>
  <!-- <BaseButton @click="isSubscribed = false" bgColor="coral">Reset</BaseButton> -->
  <section class="email-list">
    <span class="email-list__subtitle">35,000+ already joined</span>
    <h2 class="email-list__title">Stay up-to-date with what we’re doing</h2>
    <template v-if="!isSubscribed">
      <form
        class="email-list__signup"
        @submit.prevent="validateEmail"
        @keyup.enter="validateEmail"
        :class="{ invalid: !isEmailValid }"
        novalidate
      >
        <div class="input-wrapper">
          <input
            type="email"
            name="emailList"
            class="email-list__signup__email"
            placeholder="Enter your email address"
            v-model="userEnteredEmail"
            autocomplete="off"
            required
          />
          <transition name="email-alert-transition">
            <strong
              class="email-list__signup__alert"
              v-if="!isEmailValid"
              role="alert"
            >
              Whoops, make sure it's an email
            </strong>
          </transition>
        </div>
        <BaseButton
          :bgColor="'hsl(0, 94%, 66%)'"
          :width="125"
          :height="46"
          class="email-list__signup__btn"
          @click="validateEmail"
        >
          Contact Us
        </BaseButton>
      </form>
    </template>
    <transition name="thank-note-transition">
      <span class="email-list__thank-note" v-if="isSubscribed">
        Thanks for subscribing!
      </span>
    </transition>
  </section>
</template>

<script>
import BaseButton from "../Base/BaseButton.vue";
// import useVuelidate from '@vuelidate/core'
// import { required, email, minLength } from '@vuelidate/validators'

export default { 
  name: "EmailList",
  components: {
    BaseButton,
  },
  data() {
    return {
      userEnteredEmail: "",
      isEmailValid: true,
      isSubscribed: false,
    };
  },
  methods: {
    validateEmail() {
      const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      const isValid = pattern.test(String(this.userEnteredEmail).toLowerCase());
      this.isEmailValid = isValid;
      this.isSubscribed = isValid;
    },
  },
  // validations: {
  //   userEnteredEmail: {
  //     required,
  //     email,
  //     minLength: minLength(5),
  //   },
  // },
};
</script>

<style lang="scss">

.input-wrapper::after {
  content: url("../../assets/images/icon-error.svg");
  position: absolute;
  right: 10px;
  transform: translateY(50%) scale(0);
  transform-origin: center;
  transition: transform 150ms;
}

.invalid .input-wrapper::after {
  transform: translateY(50%) scale(1);
}

</style>
