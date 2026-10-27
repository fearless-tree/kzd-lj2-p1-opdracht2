<script setup>
const cards = [
  {
    title: 'CONSTRUCTION',
    image: '/assets/construction.png',
    text: 'We specialize in all kinds of construction works. Our certified team provides the services in time and on the highest level.',
  },
  {
    title: 'ABOUT US',
    image: '/assets/crane.png',
    text: 'BuildIcon is a client-oriented company. We meet schedule deadlines and work with care and quality.',
  },
  {
    title: 'EFFECTIVE TEAMWORK',
    image: '/assets/team.png',
    text: 'We have a strong team spirit and work together to find the best solutions for every project.',
  },
];
</script>

<template>
  <section id="about" class="about-section">
    <div class="container grid three-columns about-grid">
      <article v-for="card in cards" :key="card.title" class="about-card">
        <img :src="card.image" :alt="card.title" />
        <div class="about-card-body">
          <h2>{{ card.title }}</h2>
          <span class="gold-line"></span>
          <p>{{ card.text }}</p>
          <a class="button button-gold" href="#projects">LEARN MORE ❯</a>
        </div>
      </article>
    </div>
  </section>
</template>
