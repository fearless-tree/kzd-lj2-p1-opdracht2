<script setup>
import { ref } from 'vue';

const slides = [
  { image: '/assets/hero.png', line1: 'Constructing', line2: 'Is Our Life Business' },
  { image: '/assets/crane.png', line1: 'Building Better', line2: 'For The Future' },
];
const activeSlide = ref(0);

function changeSlide(direction) {
  activeSlide.value = (activeSlide.value + direction + slides.length) % slides.length;
}
</script>

<template>
  <section
    id="home"
    class="hero"
    :style="{
      backgroundImage: `linear-gradient(90deg, rgba(255,255,255,.44), transparent 65%), url('${slides[activeSlide].image}')`,
    }"
  >
    <div class="container hero-inner">
      <p class="hero-kicker">HIGH QUALITY GARANTIED</p>
      <h1>{{ slides[activeSlide].line1 }}<br />{{ slides[activeSlide].line2 }}</h1>
      <div class="hero-buttons">
        <a class="button button-gold" href="#about">OUR SERVICES ❯</a>
        <a class="button button-dark" href="#about">ABOUT US ❯</a>
      </div>
    </div>
    <button class="hero-arrow hero-prev" type="button" aria-label="Previous slide" @click="changeSlide(-1)">‹</button>
    <button class="hero-arrow hero-next" type="button" aria-label="Next slide" @click="changeSlide(1)">›</button>
  </section>
</template>
