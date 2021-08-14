<template>
  <li :class="{ expanded: expanded }">
    <button class="accordion-question" @click="expanded = !expanded">
      <span class="accordion-question__text"> {{ question }} </span>
      <span class="accordion-question__arrow-icon">
        <IconArrow />
      </span>
    </button>
    <transition name="answer-transition">
      <div class="accordion-answer" v-show="expanded">
        <p>{{ answer }}</p>
      </div>
    </transition>
  </li>
</template>

<script>
import IconArrow from "./icons/IconArrow.vue";

export default {
  name: "AccordionItem",
  components: {
    IconArrow
  },
  props: {
    question: {
      type: String,
      required: true,
    },
    answer: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      expanded: false,
    };
  },
};
</script>

<style lang="scss">
@use '../assets/sass/abstracts/all.scss' as *;
@use '../assets/sass/base/helpers.scss' as *;

.accordion-question {
  all: unset;
  width: 100%;
  padding: 20px 0;
  border-top: 1.3px solid lighten($grayish-blue, 30);
  color: $very-dark-blue;
  cursor: pointer;
  transition: color 250ms;
  @include flexbox(null, space-between);
  @include font-size($p-font-sizes);

  &:hover,
  &:focus {
    color: $soft-red;
  }
}

.accordion-question__arrow-icon {
  min-width: 50px;
  @extend %grid-center;
  transition: transform 250ms linear;
  color: #5267DF;
}

.expanded .accordion-question__arrow-icon {
  color: $soft-red;
  transform: rotate(-0.5turn);
}

.accordion-answer {
  @extend %primary-paragraph;
  overflow: hidden;

  > p {
    padding-bottom: 20px;
  }
}

.answer-transition-enter-active {
  transition: all 0.3s ease-out;
}

.answer-transition-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.answer-transition-enter-from,
.answer-transition-leave-to {
  transform: translateX(20px);
  height: 0;
  opacity: 0;
}
</style>