<template>
  <section class="hero-section">
    <div class="container">
      <!-- "header-height" for mobile-->
      <header :class="{ 'header-height': menuDisplay }">
        <div class="logo">
          <img src="../Images/logo.png" alt="" />
        </div>
        <nav :class="{ show: menuDisplay }">
          <ul>
            <li>products <i class="bi bi-chevron-down"></i></li>
            <li>solutions <i class="bi bi-chevron-down"></i></li>
            <li>Resources<i class="bi bi-chevron-down"></i></li>
            <li>pricing</li>
          </ul>
        </nav>
        <div class="header-action-btn" :class="{ show: menuDisplay }">
          <button class="sales me-3">Talk to Sales</button>
          <button class="sign-up">sign up for free</button>
        </div>
        <div class="menu-icon mb-3">
          <i class="bi bi-menu-button-wide" @click="showMenu"></i>
        </div>
      </header>
      <div class="row hero-content-wrapper g-5">
        <div class="col-lg-6">
          <h1>Uniting the world, <br />one video call at a time</h1>
          <p>
            Experience the future of communication with ClearLink - where
            crystal-clear video conferencing meets unparalleled simplicity.
          </p>
          <button class="action-trial">Start your free trial</button>
          <button class="action-ai">
            <i class="bi bi-robot"></i>Discover Ai assistant
          </button>
          <div class="rating-container">
            <img src="../Images/Avatar.png" alt="" />
            <span class="rating">
              <span>
                <i class="bi bi-star-fill"></i>
                <i class="bi bi-star-fill"></i>
                <i class="bi bi-star-fill"></i>
                <i class="bi bi-star-fill"></i>
                <i class="bi bi-star-fill"></i>
                5.0
              </span>
              <span class="rating-span">from 3,000+ reviews</span>
            </span>
          </div>
        </div>
        <div class="col-lg-6">
          <div class="avatar-gallary">
            <div class="row">
              <div class="col-4 avatar-img-cont avatar-img-wrapper-1 me-3">
                <img src="../Images/avatar-1.png" alt="" />
              </div>
              <div class="col-4 avatar-img-cont avatar-img-wrapper-2 me-3">
                <img src="../Images/avatar-2.png" alt="" />
              </div>
              <div class="col-4 avatar-img-cont avatar-img-wrapper-3">
                <img src="../Images/avatar-3.png" alt="" />
              </div>
            </div>
            <div class="row mt-3">
              <div class="col-4 avatar-img-cont avatar-img-wrapper-4 me-3">
                <img src="../Images/avatar-4.png" alt="" />
              </div>
              <div class="col-4 avatar-img-cont avatar-img-wrapper-5 me-3">
                <img src="../Images/avatar-5.png" alt="" />
              </div>
              <div class="col-4 avatar-img-cont avatar-img-wrapper-6">
                <img src="../Images/avatar-6.png" alt="" />
              </div>
            </div>
            <div class="avatar-icon-wrapper">
              <div class="avatar-icon-box">
                <i class="bi bi-mic"></i>
              </div>
              <div class="avatar-icon-box">
                <i class="bi bi-camera-video"></i>
              </div>
              <div class="avatar-icon-box">
                <i class="bi bi-tv"></i>
              </div>
              <div class="avatar-icon-box">
                <i class="bi bi-emoji-smile"></i>
              </div>
              <div class="avatar-icon-box">
                <i class="bi bi-chat-text"></i>
              </div>
              <div class="avatar-icon-box">
                <i class="bi bi-gear"></i>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
let menuDisplay = ref(false);
const showMenu = function () {
  menuDisplay.value = !menuDisplay.value;
};
</script>
