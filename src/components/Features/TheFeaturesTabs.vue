<template>
  <div class="tab">
    <div class="section">
      <h4
        class="section__item"
        @click.prevent="setActive('section-1')"
        :class="{ active: isActive('section-1') }"
        href="#section-1"
      >
        Simple Bookmarking
      </h4>

      <h4
        class="section__item"
        @click.prevent="setActive('section-2')"
        :class="{ active: isActive('section-2') }"
        href="#section-2"
      >
        Speedy Searching
      </h4>

      <h4
        class="section__item"
        @click.prevent="setActive('section-3')"
        :class="{ active: isActive('section-3') }"
        href="#section-3"
      >
        Easy Sharing
      </h4>
    </div>

    <div class="panel" id="myTabContent">
      <!--Section-->
      <div
        class="panel__section"
        :class="{ 'active show': isActive('section-1') }"
        id="section-1"
      >
        <img
          class="panel__section-img"
          src="../../assets/images/illustration-features-tab-1.svg"
          alt=""
        />
        <div class="panel__container">
          <h3 class="panel__container-title">Bookmark in one click</h3>
          <p class="panel__container-text">
            Organize your bookmarks however you like. Our simple drag-and-drop
            interface gives you complete control over how you manage your
            favourite sites.
          </p>
          <BaseButton type="link" class="panel__more-info">More Info</BaseButton>
        </div>
      </div>

      <!--Section-->
      <div
        class="panel__section"
        :class="{ 'active show': isActive('section-2') }"
        id="section-2"
      >
        <img
          class="panel__section-img"
          src="../../assets/images/illustration-features-tab-2.svg"
          alt=""
        />
        <div class="panel__container">
          <h3 class="panel__container-title">Intelligent search</h3>
          <p class="panel__container-text">
            Our powerful search feature will help you find saved sites in no
            time at all. No need to trawl through all of your bookmarks.
          </p>
          <BaseButton type="link">More Info</BaseButton>
        </div>
      </div>

      <!--Section-->
      <div
        class="panel__section "
        :class="{ 'active show': isActive('section-3') }"
        id="section-3"
      >
        <img
          class="panel__section-img"
          src="../../assets/images/illustration-features-tab-3.svg"
          alt=""
        />
        <div class="panel__container">
          <h3 class="panel__container-title">Share your bookmarks</h3>
          <p class="panel__container-text">
            Easily share your bookmarks and collections with others. Create a
            shareable link that you can send at the click of a button.
          </p>
          <BaseButton type="link">More Info</BaseButton>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BaseButton from "../Base/BaseButton.vue";

export default {
  name: "Tabs",
  components: { BaseButton },

  data() {
    return {
      activeItem: "section-1",
    };
  },

  methods: {
    isActive(menuItem) {
      return this.activeItem === menuItem;
    },
    setActive(menuItem) {
      this.activeItem = menuItem;
    },
  },
};
</script>
