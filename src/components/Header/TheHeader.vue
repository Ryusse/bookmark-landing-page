<template>
  <header class="header" ref="header">
    <Navbar :navLinks="navLinks" />
  </header>
</template>

<script>
import Navbar from "./TheHeaderNavbar.vue";

export default {
  name: "TheHeader",
  components: {
    Navbar,
  },
  data() {
    return {
      navLinks: ["features", "pricing", "contact"],
    };
  },
};
</script>
