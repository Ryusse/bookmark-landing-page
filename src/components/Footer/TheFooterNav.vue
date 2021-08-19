<template>
  <aside class="footer__aside">
    <div class="footer__aside__container">
      <span class="footer__aside__logo-wrapper">
        <a href="#" class="footer__aside__logo">
          <img src="../../assets/images/logo-bookmark-white.svg" alt="bookmark" />
        </a>
      </span>
      <nav class="footer__nav">
        <ul class="footer__nav__ul">
          <li class="footer__nav__ul__li" v-for="item in navList" :key="item">
            <a :href="`#${item}`">{{ item }}</a>
          </li>
        </ul>
      </nav>
      <div class="footer__sm-icons">
        <a href="#" title="follow us on facebook">
          <IconFacebook />
        </a>
        <a href="#" title="follow us on twitter">
          <IconTwitter />
        </a>
      </div>
    </div>
  </aside>
</template>

<script>
import IconFacebook from '../icons/IconFacebook.vue';
import IconTwitter from "../icons/IconTwitter.vue";

export default {
  name: "FooterNav",
  components: {
    IconFacebook,
    IconTwitter
  },
  data() {
    return {
      navList: ["features", "pricing", "contact"],
    };
  },
};
</script>
