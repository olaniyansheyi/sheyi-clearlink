<template>
  <section class="testimonial">
    <div class="container">
      <div class="row gy-5">
        <div class="col-lg-6">
          <span class="shoppify">
            <img src="../Images/shoppify-no-bg.png" alt="" />
            <h3>shopify</h3>
          </span>
          <div class="rating">
            <span>
              <i class="bi bi-star-fill"></i>
              <i class="bi bi-star-fill"></i>
              <i class="bi bi-star-fill"></i>
              <i class="bi bi-star-fill"></i>
              <i class="bi bi-star-fill"></i>
            </span>
          </div>
          <h4>
            ClearLink has upgraded our remote meetings. High-quality video,
            screen sharing, and top-notch security make it essential for our
            team.
          </h4>
          <div class="testimonial-slider">
            <div class="testimonial-box">
              <!-- <img :src="currentTestimonial.avatar" /> -->
              <img src="../Images/Avatar.png" alt="" />
              <span>
                <h5>{{ currentTestimonial.name }}</h5>
                <p>{{ currentTestimonial.position }}</p>
              </span>
            </div>
            <div class="btn-slider d-flex">
              <div class="btn-slider-wrapper" @click="previous">
                <i class="bi bi-arrow-left"></i>
              </div>
              <div class="btn-slider-wrapper">
                <i class="bi bi-arrow-right" @click="next"></i>
              </div>
            </div>
          </div>
        </div>
        <div class="col-lg-6">
          <!-- <img :src="currentTestimonial.avatar" alt="" /> -->
          <img src="../Images/Contents.png" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted, computed } from "vue";
const testimonials = ref([
  {
    name: "Sarah Thomson",
    position: "product Manager, shopify",
    avatar: "../Images/Avatar.png",
  },
  {
    name: "Danial wilson",
    position: "Frontend developer, Google",
    avatar: "../Images/Avatar.png",
  },
  {
    name: "David mark",
    position: "Data analyst, Jumia",
    avatar: "../Images/Avatar.png",
  },
]);
let currentSlide = ref(0);
const currentTestimonial = computed(
  () => testimonials.value[currentSlide.value]
);
const next = () => {
  currentSlide.value = (currentSlide.value + 1) % testimonials.value.length;
};
const previous = () => {
  currentSlide.value =
    (currentSlide.value - 1 + testimonials.value.length) %
    testimonials.value.length;
};

const startAutoScroll = () => {
  const autoScrollInterval = setInterval(next, 1700);
};

const stopAutoScroll = () => {
  clearInterval(autoScrollInterval);
};

onMounted(() => {
  startAutoScroll();
});

onUnmounted(() => {
  stopAutoScroll();
});
</script>
