<script setup>
import { onMounted } from 'vue';
import Hero from '../components/Hero.vue';
import Features from '../components/Features.vue';
import Catalog from '../components/Catalog.vue';
import Testimonials from '../components/Testimonials.vue';
import Faqs from '../components/Faqs.vue';
import AboutContact from '../components/AboutContact.vue';

onMounted(() => {
  // Intersection Observer for scroll animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('in-view');
      } else {
        entry.target.classList.remove('in-view');
      }
    });
  }, {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
  });

  // Observe all elements with .animate-on-scroll class after mounting
  setTimeout(() => {
    document.querySelectorAll('.animate-on-scroll').forEach(el => {
      observer.observe(el);
    });
  }, 150);
});
</script>

<template>
  <div class="home-page">
    <Hero />
    <Features />
    <Catalog />
    <Testimonials />
    <Faqs />
    <AboutContact />
  </div>
</template>
