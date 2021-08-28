<template>
  <div :style="{ color: bgColor }"><!-- to inherit color -->
    <button v-if="type === 'button'" :style="btnStyles" class="base-btn">
      <slot></slot>
    </button>
    <a
      v-else-if="type === 'link'"
      :href="url"
      :style="btnStyles"
      class="base-link"
    >
      <slot></slot>
    </a>
  </div>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: "button",
    },
    width: {
      type: String,
      default: "clamp(80px, 40vw,160px)",
    },
    height: {
      type: String,
      default: "42px",
    },
    color: {
      type: String,
      default: "white",
    },
    bgColor: {
      type: String,
      default: "hsl(231, 69%, 60%)",
    },
    url: {
      type: String,
      default: "#",
    },
  },
  data() {
    return {
      btnStyles: {
        width: this.width,
        height: this.height,
        color: this.color,
        backgroundColor: this.bgColor,
        borderColor: this.bgColor,
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.base-btn,
.base-link {
  $delay: 500ms;
  margin: 10px 0;
  text-align: center;
  border-radius: 5px;
  border-width: 2px;
  border-style: solid;
  transition: background-color $delay, color $delay, border $delay;
  box-shadow: 0px 4px 10px #00000029;
  font-weight: 500;
  font-size: clamp(0.85rem, 2.1vw, 0.9rem);
  outline: transparent;
  user-select: none;
  text-decoration: none;
  display: flex;
  justify-content: center;
  align-items: center;

  &:hover,
  &:focus-visible {
    background-color: transparent !important; // override inline styles
    color: inherit !important; // override inline styles
  }
}
</style>
