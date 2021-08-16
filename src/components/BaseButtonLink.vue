<template>
  <span :style="{ color: bgColor }"> <!-- to inherit color -->
    <a :href="url" :style="btnStyles" :class="$style['base-link']">
      <slot></slot>
    </a>
  </span>
</template>

<script>
export default {
  props: {
    url: {
      type: String,
      default: '#'
    },
    width: {
      type: Number,
      default: 160,
    },
    height: {
      type: Number,
      default: 42,
    },
    color: {
      type: String,
      default: "white",
    },
    bgColor: {
      type: String,
      default: "hsl(231, 69%, 60%)",
    },
  },
  data() {
    return {
      btnStyles: {
        width: `${this.width}px`,
        height: `${this.height}px`,
        color: this.color,
        backgroundColor: this.bgColor,
        borderColor: this.bgColor,
      },
    };
  },
};
</script>

<style lang="scss" module>

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
  font-size: clamp(.85rem, 2.1vw, .9rem);
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

  @media screen and (max-width: 400px) {
    width: 40vw !important; // override
  }
}

</style>