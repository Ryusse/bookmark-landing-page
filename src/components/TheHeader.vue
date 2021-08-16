<template>
  <header class="header">
    <Navbar />
  </header>
</template>

<script>
import Navbar from "./TheHeaderNavbar.vue";

export default {
  name: "TheHeader",
  components: {
    Navbar,
  },
};
</script>
