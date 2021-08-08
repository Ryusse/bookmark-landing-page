<template>
  <header class="header">
    <div class="logo">
      <img src="../assets/images/logo-bookmark.svg" alt="" />
    </div>

    <nav class="nav">
      <ul class="nav__list">
        <li class="nav__item"><a href="#" class="nav__link">Features</a></li>
        <li class="nav__item"><a href="#" class="nav__link">Pricing</a></li>
        <li class="nav__item"><a href="#" class="nav__link">Contact</a></li>
      </ul>
    </nav>

    <div class="menu">
      <img src="../assets/images/icon-hamburger.svg" alt="" />
    </div>

  </header>
</template>

<script>


export default {

  name: "TheHeader",

  data() {
    return {
      button: "Login",
    };
  },
};
</script>

<style scoped lang="scss">

</style>
