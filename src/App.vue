<script setup>
import SiteHeader from './components/SiteHeader.vue';
import HeroBanner from './components/HeroBanner.vue';
import AboutCards from './components/AboutCards.vue';
import FeaturedProjects from './components/FeaturedProjects.vue';
</script>

<template>
  <SiteHeader />
  <main>
    <HeroBanner />
    <section class="intro-strip">
      <div class="container intro-inner">
        <h2>We Are <strong>BuildIcon</strong></h2>
        <p>We have been transforming ideas and visions into award-winning projects.</p>
        <a class="button button-gold" href="#contact">✉ &nbsp; REQUEST A QUOTE</a>
      </div>
    </section>
    <AboutCards />
    <FeaturedProjects />
  </main>
  <footer id="contact">
    <div class="container footer-inner">
      <strong>BuildIcon</strong>
      <span>Construction Company</span>
      <a href="mailto:hello@buildicon.example">hello@buildicon.example</a>
    </div>
  </footer>
  <a class="back-to-top" href="#home" aria-label="Back to top">↑ TOP</a>
</template>
