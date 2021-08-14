<template>
  <div class="switch">
    <!--Switch section-->
    <div class="section">
      <!--Switch section name-->
      <div
        class="section__name"
        v-for="(section, index) in sections"
        v-bind:key="index"
      >
        {{ section.item }}
      </div>
      <!--Switch section name end-->
    </div>
    <!--Switch section end-->

    <!--Switch section content-->
    <div
      class="content"
      v-for="(content, index) in contents"
      v-bind:key="index"
    >
      <img class="content__image" :src="content.image" />
      <h3 class="content__title">{{ content.title }}</h3>
      <p class="content__text">{{ content.text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Switch",

  data() {
    return {
      sections: [
        {
          item: "Simple Bookmarking",
        },
        {
          item: "Speedy Searching",
        },
        {
          item: "Easy Sharing",
        },
      ],

      contents: [
        {
          image: require("../assets/images/illustration-features-tab-1.svg"),
          title: "Bookmark in one click",
          text: "Organize your bookmarks however you like. Our simple drag-and-drop interface gives you complete control over how you manage your favourite sites.",
        },
        {
          image: require("../assets/images/illustration-features-tab-2.svg"),
          title: "Intelligent search",
          text: "Our powerful search feature will help you find saved sites in no time at all. No need to trawl through all of your bookmarks.",
        },
        {
          image: require("../assets/images/illustration-features-tab-3.svg"),
          title: "Share your bookmarks",
          text: "Easily share your bookmarks and collections with others. Create a shareable link that you can send at the click of a button.",
        },
      ],
    };
  },
};
</script>


<style>
</style>