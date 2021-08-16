<template>
  <li :class="{ expanded: expanded }">
    <button
      class="accordion-question"
      @click="toggleQuestion"
      @keyup.space="toggleQuestion"
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
  data() {
    return {
      expanded: false,
    };
  },
  methods: {
    toggleQuestion() {
      this.expanded = !this.expanded;
    },
  },
};
</script>
