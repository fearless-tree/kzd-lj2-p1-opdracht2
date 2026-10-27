<script setup>
import { computed, ref } from 'vue';

const filters = ['ALL', 'BUILDING', 'CONSULTING', 'INTERIOR', 'OFFICE'];
const selected = ref('ALL');
const projects = [
  {
    title: 'Coastal Residence',
    category: 'BUILDING',
    image: '/assets/villa.png',
    text: 'A bright contemporary home with careful attention to every detail.',
  },
  {
    title: 'City Construction',
    category: 'CONSULTING',
    image: '/assets/crane.png',
    text: 'Planning and building a strong foundation for a growing city.',
  },
  {
    title: 'Modern Living',
    category: 'BUILDING',
    image: '/assets/villa.png',
    text: 'A modern residence designed for comfort and lasting quality.',
  },
  {
    title: 'Construction Works',
    category: 'CONSULTING',
    image: '/assets/construction.png',
    text: 'Our team solves each challenge through practical cooperation.',
  },
  {
    title: 'Warm Interior',
    category: 'INTERIOR',
    image: '/assets/interior.png',
    text: 'A calm interior where natural light meets simple materials.',
  },
  {
    title: 'The BuildIcon Team',
    category: 'OFFICE',
    image: '/assets/team.png',
    text: 'People working together to bring every project to life.',
  },
];
const visibleProjects = computed(() =>
  selected.value === 'ALL' ? projects : projects.filter((project) => project.category === selected.value)
);
</script>

<template>
  <section id="projects" class="projects-section">
    <div class="projects-heading">
      <h2>FEATURED PROJECTS</h2>
      <div class="project-filters" role="group" aria-label="Filter projects">
        <button
          v-for="filter in filters"
          :key="filter"
          type="button"
          :class="{ active: selected === filter }"
          :aria-pressed="selected === filter"
          @click="selected = filter"
        >
          {{ filter }}
        </button>
      </div>
    </div>
    <div class="grid three-columns project-grid">
      <article v-for="project in visibleProjects" :key="project.title" class="project-card" tabindex="0">
        <img :src="project.image" :alt="project.title" />
        <div class="project-overlay">
          <h3>{{ project.title }}</h3>
          <p>{{ project.text }}</p>
          <a href="#contact">LEARN MORE ❯</a>
        </div>
      </article>
    </div>
  </section>
</template>
