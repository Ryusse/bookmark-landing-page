<template>
  <header class="header">
    <Navbar />
  </header>
</template>

<script>
import Navbar from "../components/Navbar.vue";

export default {
  name: "TheHeader",
  components: {
    Navbar,
  },

  data() {
    return {
      Menu: [
        {
          title: "Features",
          link: "#",
        },
        {
          title: "Pricing",
          link: "#",
        },
        {
          title: "Contact",
          link: "#",
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss"></style>
