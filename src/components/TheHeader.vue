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
