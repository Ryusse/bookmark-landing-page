<template>
  <footer class="footer">
    <EmailList />
    <FooterNav />
  </footer>
</template>

<script>
import EmailList from "./TheFooterEmailList.vue";
import FooterNav from "./TheFooterNav.vue";

export default {
  name: "TheFooter",
  components: {
    EmailList,
    FooterNav
  }
}
</script>