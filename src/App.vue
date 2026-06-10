<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import Features from './components/Features.vue';
import Catalog from './components/Catalog.vue';
import Testimonials from './components/Testimonials.vue';
import Faqs from './components/Faqs.vue';
import AboutContact from './components/AboutContact.vue';
import Footer from './components/Footer.vue';

const showScrollTop = ref(false);
const scrollProgress = ref(0);

const handleScroll = () => {
  // Toggle "Scroll to Top" button
  showScrollTop.value = window.scrollY > 400;

  // Calculate scroll progress percentage
  const totalHeight = document.documentElement.scrollHeight - window.innerHeight;
  if (totalHeight > 0) {
    scrollProgress.value = (window.scrollY / totalHeight) * 100;
  }
};

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  });
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
  handleScroll(); // Initial call

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

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <div class="app-layout">
    <!-- Scroll Progress Indicator -->
    <div class="scroll-progress-container">
      <div class="scroll-progress-bar" :style="{ width: scrollProgress + '%' }"></div>
    </div>

    <!-- Sticky Navigation Bar -->
    <Navbar />

    <!-- Main Content Area -->
    <main class="main-content">
      <Hero />
      <Features />
      <Catalog />
      <Testimonials />
      <Faqs />
      <AboutContact />
    </main>

    <!-- Footer Area -->
    <Footer />

    <!-- Floating Action Widgets -->
    <div class="floating-widgets">
      <!-- Back to Top Button -->
      <button 
        @click="scrollToTop" 
        :class="['scroll-top-btn', 'glass', { visible: showScrollTop }]"
        aria-label="Scroll to top"
      >
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="w-6 h-6">
          <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 15.75l7.5-7.5 7.5 7.5" />
        </svg>
      </button>

      <!-- Floating WhatsApp widget -->
      <div class="floating-wa-container">
        <a 
          href="https://wa.me/6281913842931?text=Halo%20Anom%20Elektronik%2C%20saya%20butuh%20bantuan%20mengenai%20produk%20Anda." 
          target="_blank" 
          rel="noopener noreferrer" 
          class="floating-wa-btn"
        >
          <!-- WhatsApp Icon -->
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 16 16" class="wa-icon">
            <path d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.933 7.933 0 0 0 3.79.977h.004c4.368 0 7.926-3.559 7.93-7.934A7.897 7.897 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.69-4.869c-.202-.103-1.202-.594-1.385-.658-.182-.066-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.09-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.252-.017-.353-.05-.101-.445-1.076-.61-1.478-.161-.389-.324-.336-.445-.342-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.202-.491 1.372-1.02.17-.528.17-1.011.12-1.099-.051-.088-.183-.134-.38-.237z"/>
          </svg>
          <!-- Hover message tooltip -->
          <span class="wa-tooltip">Ada pertanyaan? Chat Kami!</span>
        </a>
      </div>
    </div>
  </div>
</template>

<style>
/* Global App layout styles */
.app-layout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.main-content {
  flex-grow: 1;
}

/* Scroll progress indicator style */
.scroll-progress-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 3px;
  z-index: 101;
  background-color: transparent;
}

.scroll-progress-bar {
  height: 100%;
  background-color: var(--primary);
  transition: width 0.05s ease-out;
  width: 0%;
}

/* Floating Action widgets styling */
.floating-widgets {
  position: fixed;
  bottom: 24px;
  right: 24px;
  display: flex;
  flex-direction: column;
  gap: 16px;
  z-index: 90;
}

.scroll-top-btn {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--text-strong);
  cursor: pointer;
  opacity: 0;
  transform: translateY(20px);
  pointer-events: none;
  transition: opacity var(--transition-fast), transform var(--transition-fast), background-color var(--transition-fast);
  box-shadow: var(--shadow-md);
}

.scroll-top-btn.visible {
  opacity: 1;
  transform: translateY(0);
  pointer-events: auto;
}

.scroll-top-btn:hover {
  background-color: var(--primary);
  color: var(--text-white);
  border-color: transparent;
}

/* Floating WA button with greeting */
.floating-wa-container {
  position: relative;
}

.floating-wa-btn {
  width: 54px;
  height: 54px;
  border-radius: 50%;
  background-color: #25d366;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 16px rgba(37, 211, 102, 0.4);
  cursor: pointer;
  transition: transform var(--transition-fast), box-shadow var(--transition-fast);
}

.floating-wa-btn:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 20px rgba(37, 211, 102, 0.6);
}

.wa-icon {
  width: 28px;
  height: 28px;
}

/* Tooltip message */
.wa-tooltip {
  position: absolute;
  right: 66px;
  top: 50%;
  transform: translateY(-50%) translateX(10px);
  background-color: var(--bg-card);
  border: 1px solid var(--border);
  color: var(--text-strong);
  font-size: 0.8rem;
  font-weight: 700;
  padding: 8px 16px;
  border-radius: var(--radius-sm);
  white-space: nowrap;
  box-shadow: var(--shadow-md);
  opacity: 0;
  pointer-events: none;
  transition: opacity var(--transition-fast), transform var(--transition-fast);
}

.floating-wa-container:hover .wa-tooltip {
  opacity: 1;
  transform: translateY(-50%) translateX(0);
}

/* Responsive adjustment */
@media (max-width: 576px) {
  .floating-widgets {
    bottom: 16px;
    right: 16px;
    gap: 12px;
  }
  
  .scroll-top-btn {
    width: 40px;
    height: 40px;
  }
  
  .floating-wa-btn {
    width: 46px;
    height: 46px;
  }
  
  .wa-icon {
    width: 22px;
    height: 22px;
  }
  
  .wa-tooltip {
    display: none; /* Hide greeting bubble on mobile to avoid covering content */
  }
}
</style>
