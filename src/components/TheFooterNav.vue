<template>
  <aside class="footer__aside">
    <a href="#" class="footer__aside__logo">
      <img src="../assets/images/logo-bookmark-white.svg" alt="bookmark" />
    </a>
    <nav class="footer__nav">
      <ul class="footer__nav__ul">
        <li class="footer__nav__ul__li" v-for="item in navList" :key="item">
          <a href="#">{{ item }}</a>
        </li>
      </ul>
    </nav>
    <div class="footer__sm-icons">
      <a href="#" title="follow us on facebook">
        <img src="../assets/images/icon-facebook.svg" alt="" />
      </a>
      <a href="#" title="follow us on twitter">
        <img src="../assets/images/icon-twitter.svg" alt="" />
      </a>
    </div>
  </aside>
</template>

<script>
export default {
  name: "FooterNav",
  data() {
    return {
      navList: ["Features", "Pricing", "Contact"],
    };
  },
};
</script>
