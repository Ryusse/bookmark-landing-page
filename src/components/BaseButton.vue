<template>
  <div :style="{ color: bgColor }"> <!-- to inserit color -->
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
      default: 161,
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
        color: this.color,
        backgroundColor: this.bgColor,
        width: `${this.width}px`,
        borderColor: this.bgColor,
      },
    };
  },
};
</script>

<style lang="scss" module>
html {
  font-family: sans-serif;
}

body {
  display: grid;
  place-items: center;
  min-height: 100vh;
}

.base-btn {
  all: unset;
  margin: 10px;
  height: 41px;
  text-align: center;
  cursor: pointer;
  border-radius: 5px;
  border-width: 3px;
  border-style: solid;
  transition: all 300ms;

  &:hover {
    background-color: transparent !important; // override inline styles
    color: inherit !important; // override inline styles
  }
}
</style>
