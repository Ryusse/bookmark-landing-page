<template>
  <nav class="navbar">
    <div class="logo">
      <IconLogo :isActive="showMobileMenu" />
    </div>

    <!--Navbar Links Desktop-->
    <ul class="navbar__list">
      <li class="navbar__item" v-for="(navLink, i) in navLinks" :key="i">
        <a :href="`#${navLink}`" class="navbar__link">{{ navLink }}</a>
      </li>
      <li class="navbar__item">
        <BaseButton
          type="link"
          class="button--login navbar__link"
          :bgColor="colors.softRed"
          width="111px"
        >
          Login
        </BaseButton>
      </li>
    </ul>

    <!--Menu Burger-->
    <button
      class="burger"
      :class="{ active: showMobileMenu}"
      @click="showMobileMenu = !showMobileMenu"
    >
      <IconClose v-if="showMobileMenu" />
      <IconMenu v-else />
    </button>

    <!--Navbar links Mobile-->
    <div class="menu" :class="{ active: showMobileMenu }">
      <ul class="menu__list">
        <li class="menu__item" v-for="(navLink, i) in navLinks" :key="i">
          <a
            :href="`#${navLink}`"
            class="menu__link"
            @click="showMobileMenu = false"
          >
            {{ navLink }}
          </a>
        </li>
        <li class="menu__item">
          <BaseButton
            type="link"
            class="menu__link button--login"
            bgColor="transparent"
            width="111px"
            height="46px"
          >
            Login
          </BaseButton>
        </li>
      </ul>

      <div class="menu__social" :class="{ active: showMobileMenu }">
        <a href="#" aria-label="follow us on facebook">
          <IconFacebook />
        </a>
        <a href="#" aria-label="follow us on twitter">
          <IconTwitter />
        </a>
      </div>
    </div>
  </nav>
</template>

<script>
import IconLogo from "../icons/TheHeaderLogo.vue";
import IconMenu from "../icons/IconHamMenu.vue";
import IconClose from "../icons/IconClose.vue";
import BaseButton from "../Base/BaseButton.vue";
import IconFacebook from "../icons/IconFacebook.vue";
import IconTwitter from "../icons/IconTwitter.vue";

export default {
  name: "Navbar",
  props: {
    navLinks: Array,
  },
  components: {
    IconLogo,
    IconMenu,
    IconClose,
    BaseButton,
    IconFacebook,
    IconTwitter,
  },

  data() {
    return {
      showMobileMenu: false,

      colors: {
        softRed: "hsl(0, 94%, 66%)",
      },
    };
  },
};
</script>