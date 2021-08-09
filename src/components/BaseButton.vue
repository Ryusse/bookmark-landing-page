<template>
  <div :style="{ color: bgColor }"> <!-- to inherit color -->
    <button :style="btnStyles" :class="$style['base-btn']">
      <slot></slot>
    </button>
  </div>
</template>

<script>
export default {
  props: {
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

.base-btn {
  all: unset;
  margin: 10px 0;
  text-align: center;
  cursor: pointer;
  border-radius: 5px;
  border-width: 2px;
  border-style: solid;
  transition: all 500ms;
  box-shadow: 0px 4px 10px #00000029;
  font-weight: 500;
  font-size: clamp(.85rem, 2.1vw, .9rem);

  &:hover,
  &:focus {
    background-color: transparent !important; // override inline styles
    color: inherit !important; // override inline styles
  }

  @media screen and (max-width: 400px) {
    width: 40vw !important; // override
  }
}

</style>
