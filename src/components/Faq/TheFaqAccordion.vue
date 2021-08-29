<template>
  <li :class="{ expanded: expanded }">
    <button
      class="accordion-question"
      @click="toggleAnswer"
      @keyup.space="toggleAnswer"
      :aria-expanded="expanded"
    >
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
import { ref } from "vue";
import IconArrow from "../icons/IconArrow.vue";

export default {
  name: "AccordionItem",
  components: {
    IconArrow,
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
  setup() {
    const expanded = ref(false);
    const toggleAnswer = () => expanded.value = !expanded.value;
    return { expanded, toggleAnswer }
  },
};
</script>
