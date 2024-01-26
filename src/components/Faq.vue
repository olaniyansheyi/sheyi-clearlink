<template>
  <section class="faq mt-5">
    <div class="container">
      <div class="row pt-5">
        <div class="col-lg-6">
          <div class="intro-heading">
            <span>support</span>
            <h2>FAQs</h2>
            <p>
              Everything you need to know about the product and billing. Can’t
              find the <br />
              answer you’re looking for? Please chat to our friendly team.
            </p>
          </div>
        </div>
        <div class="col-lg-6 faq-container">
          <div
            class="question"
            v-for="(faq, index) in faqs"
            :class="{ 'active-faq': faq.showContent }"
          >
            <span>
              <h6>{{ faq.question }}</h6>
              <p v-show="faq.showContent">
                {{ faq.answer }}
              </p>
            </span>
            <i
              class="bi"
              @click="toggleContent(index)"
              :class="{
                'bi-dash-circle': faq.showContent,
                'bi-plus-circle': !faq.showContent,
              }"
            ></i>
            <!-- <img src="../Images/plus-circle.png" alt=""> -->
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script setup>
import { ref } from "vue";
const faqs = ref([
  {
    question: "How many participants can join a ClearLink video conference?",
    answer: `ClearLink offers flexible meeting options. Depending on your
                subscription plan, you can host meetings with varying numbers of
                participants. Our plans are designed to accommodate small team
                collaborations and large-scale webinars, ensuring you have the
                right fit for your needs.`,
    showContent: false,
  },
  {
    question: "Can I use ClearLink on multiple devices?",
    answer: `ClearLink offers flexible meeting options. Depending on your
                subscription plan, you can host meetings with varying numbers of
                participants. Our plans are designed to accommodate small team
                collaborations and large-scale webinars, ensuring you have the
                right fit for your needs.`,
    showContent: false,
  },
  {
    question:
      "Is ClearLink compatible with other video conferencing platforms?",
    answer: `ClearLink offers flexible meeting options. Depending on your
                subscription plan, you can host meetings with varying numbers of
                participants. Our plans are designed to accommodate small team
                collaborations and large-scale webinars, ensuring you have the
                right fit for your needs.`,
    showContent: false,
  },
  {
    question: "How does ClearLink ensure the security of my video conferences?",
    answer: `ClearLink offers flexible meeting options. Depending on your
                subscription plan, you can host meetings with varying numbers of
                participants. Our plans are designed to accommodate small team
                collaborations and large-scale webinars, ensuring you have the
                right fit for your needs.`,
    showContent: false,
  },
  {
    question: "Do I need to download any software to use ClearLink?",
    answer: `ClearLink offers flexible meeting options. Depending on your
                subscription plan, you can host meetings with varying numbers of
                participants. Our plans are designed to accommodate small team
                collaborations and large-scale webinars, ensuring you have the
                right fit for your needs.`,
    showContent: false,
  },
  {
    question: "What kind of customer support does ClearLink provide?",
    answer: `ClearLink offers flexible meeting options. Depending on your
                subscription plan, you can host meetings with varying numbers of
                participants. Our plans are designed to accommodate small team
                collaborations and large-scale webinars, ensuring you have the
                right fit for your needs.`,
    showContent: false,
  },
]);

const toggleContent = function (index) {
  faqs.value.forEach((faq, i) => {
    if (i === index) {
      faqs.value[index].showContent = !faqs.value[index].showContent;
    } else {
      faq.showContent = false;
    }
  });
};
</script>
