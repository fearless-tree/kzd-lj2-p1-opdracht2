<script setup>
import { ref } from 'vue';

const menuOpen = ref(false);
</script>

<template>
  <header class="site-header">
    <div class="container masthead">
      <a class="brand" href="#home" aria-label="BuildIcon home">
        <img src="/assets/logo.png" alt="BuildIcon Construction Company" width="235" height="67" />
      </a>
      <div class="header-details">
        <div class="detail">
          <img class="detail-icon" src="/assets/icon-phone.svg" alt="" width="29" height="29" />
          <span><small>CUSTOM SUPPORT &amp; SALE</small><strong>+7-495-1234567</strong></span>
        </div>
        <div class="detail">
          <img class="detail-icon" src="/assets/icon-clock.svg" alt="" width="29" height="29" />
          <span><small>WORKING TIME</small><strong>MON–SAT: 08:00–18:00</strong></span>
        </div>
        <a class="button button-dark quote-top" href="#contact">
          <img src="/assets/icon-envelope.svg" alt="" width="14" height="14" />
          &nbsp; REQUEST A QUOTE
        </a>
      </div>
      <button
        class="menu-toggle"
        aria-controls="main-navigation"
        type="button"
        :aria-expanded="menuOpen"
        :aria-label="menuOpen ? 'Close menu' : 'Open menu'"
        @click="menuOpen = !menuOpen"
      >
        ☰
      </button>
    </div>
    <nav
      id="main-navigation"
      class="container nav-bar"
      :class="{ open: menuOpen }"
      aria-label="Main navigation"
      @click="menuOpen = false"
    >
      <a class="current" href="#home">HOME</a>
      <a href="#about">ABOUT</a>
      <a href="#about">SERVICES <span>⌄</span></a>
      <a href="#projects">PROJECTS <span>⌄</span></a>
      <a href="#projects">NEWS</a>
      <a href="#contact">CONTACT</a>
      <span class="nav-search" aria-hidden="true">⌕</span>
    </nav>
  </header>
</template>
