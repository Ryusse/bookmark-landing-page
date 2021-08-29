<template>
  <!-- <BaseButton @click="isEmailValid = !isEmailValid" bgColor="lightBlue">Toggle</BaseButton> -->
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
          bgColor="hsl(0, 94%, 66%)"
          width="125px"
          height="46px"
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
import { ref } from '@vue/reactivity';
import BaseButton from "../Base/BaseButton.vue";
// import useVuelidate from '@vuelidate/core'
// import { required, email, minLength } from '@vuelidate/validators'

export default { 
  name: "EmailList",
  components: {
    BaseButton,
  },
  setup() {
    const userEnteredEmail = ref("");
    const isEmailValid = ref(true);
    const isSubscribed = ref(false);

    const validateEmail = () => {
      const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      const isValid = pattern.test(String(userEnteredEmail.value).toLowerCase());
      isEmailValid.value = isValid;
      isSubscribed.value = isValid;
    }

    return {userEnteredEmail, isEmailValid, isSubscribed, validateEmail}
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
