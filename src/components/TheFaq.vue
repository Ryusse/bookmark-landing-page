<template>
  <section class="faq">
    <h2 class="faq__title">Frequently Asked Questions</h2>
    <p class="faq__subtitle">
      Here are some of our FAQs. If you have any other questions you’d like
      answered please feel free to email us.
    </p>
    <div class="faq__accordion">
      <ul class="faq__accordion__ul">
        <AccordionItem
          v-for="faq in faqs"
          :key="faq.question"
          :question="faq.question"
          :answer="faq.answer"
        />
      </ul>
    </div>
    <BaseButton :width="110" :height="45">More Info</BaseButton>
  </section>
</template>

<script>
import AccordionItem from "./AccordionItem.vue";
import BaseButton from "./BaseButton.vue";

export default {
  name: "TheFaq",
  components: {
    AccordionItem,
    BaseButton,
  },
  data() {
    return {
      faqs: [
        {
          question: "What is Bookmark?",
          answer: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce tincidunt justo eget ultricies fringilla. Phasellus blandit ipsum quis quam ornare mattis.",
        },
        {
          question: "How can I request a new browser?",
          answer: "Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet. Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdie tVivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet.",
        },
        {
          question: "Is there a mobile app?",
          answer: "Sed consectetur quam id neque fermentum accumsan. Praesent luctus vestibulum dolor, ut condimentum urna vulputate eget. Cras in ligula quis est pharetra mattis sit amet pharetra purus. Sed sollicitudin ex et ultricies bibendum.",
        },
        {
          question: "What about other Chromium browsers?",
          answer: "Integer condimentum ipsum id imperdiet finibus. Vivamus in placerat mi, at euismod dui. Aliquam vitae neque eget nisl gravida pellentesque non ut velit.",
        },
      ],
    };
  },
};
</script>