<script setup>
import { ref } from 'vue';

const isMobileMenuOpen = ref(false);

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false;
};
</script>

<template>
  <header class="navbar-wrapper glass">
    <div class="container navbar-container">
      <!-- Logo Section -->
      <a href="#" class="logo-area" @click="closeMobileMenu">
        <img src="/images/anom_logo.webp" alt="Anom Logo" class="logo-img" />
        <span class="logo-text">Anom<span class="highlight">Elektronik</span></span>
      </a>

      <!-- Desktop Navigation Menu -->
      <nav class="desktop-nav">
        <a href="#hero" class="nav-link">Home</a>
        <a href="#catalog" class="nav-link">Produk</a>
        <a href="#features" class="nav-link">Keunggulan</a>
        <a href="#location" class="nav-link">Kontak & Lokasi</a>
      </nav>

      <div class="nav-actions">
        <!-- WhatsApp Button -->
        <a href="https://wa.me/6281913842931?text=Halo%20Anom%20Elektronik%2C%20saya%20ingin%20bertanya%20mengenai%20ketersediaan%20stok%20barang%20di%20toko%20offline." target="_blank" rel="noopener noreferrer" class="btn-whatsapp">
          <span>Tanya Stok</span>
        </a>

        <!-- Hamburger Icon -->
        <button class="hamburger-btn" @click="toggleMobileMenu" :aria-label="isMobileMenuOpen ? 'Close Menu' : 'Open Menu'">
          <span class="hamburger-line" :class="{ 'open-top': isMobileMenuOpen }"></span>
          <span class="hamburger-line" :class="{ 'open-mid': isMobileMenuOpen }"></span>
          <span class="hamburger-line" :class="{ 'open-bot': isMobileMenuOpen }"></span>
        </button>
      </div>
    </div>

    <!-- Mobile Navigation Panel -->
    <div class="mobile-nav-panel" :class="{ 'is-open': isMobileMenuOpen }">
      <nav class="mobile-nav">
        <a href="#hero" class="mobile-link" @click="closeMobileMenu">Home</a>
        <a href="#catalog" class="mobile-link" @click="closeMobileMenu">Pilihan Produk</a>
        <a href="#features" class="mobile-link" @click="closeMobileMenu">Keunggulan kami</a>
        <a href="#location" class="mobile-link" @click="closeMobileMenu">Hubungi kami</a>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.navbar-wrapper {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 100;
  height: 70px;
  display: flex;
  align-items: center;
  border-bottom: 1px solid var(--border);
  transition: background-color var(--transition-normal), border var(--transition-normal);
}

.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-area {
  display: flex;
  align-items: center;
  gap: 10px;
  font-family: var(--font-heading);
  font-weight: 700;
  font-size: 1.25rem;
  letter-spacing: -0.5px;
  color: var(--text-strong);
}

.logo-img {
  height: 32px;
  width: 32px;
  object-fit: contain;
}

.highlight {
  color: var(--primary);
}

.desktop-nav {
  display: flex;
  gap: 32px;
}

.nav-link {
  font-weight: 500;
  font-size: 0.95rem;
  color: var(--text-muted);
  position: relative;
  padding: 8px 0;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--primary);
  transition: width var(--transition-normal);
  border-radius: var(--radius-full);
}

.nav-link:hover {
  color: var(--text-strong);
}

.nav-link:hover::after {
  width: 100%;
}

.nav-actions {
  display: flex;
  align-items: center;
  gap: 16px;
}

.icon-btn {
  padding: 8px;
  border-radius: var(--radius-sm);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--text-muted);
  transition: color var(--transition-fast), background-color var(--transition-fast);
}

.icon-btn:hover {
  color: var(--text-strong);
  background-color: var(--border);
}

.w-6 {
  width: 20px;
  height: 20px;
}

.sun-icon {
  color: #fbbf24;
}

.moon-icon {
  color: #3b82f6;
}

.btn-whatsapp {
  padding: 6px 14px;
  background-color: #25d366;
  color: var(--text-white);
  font-weight: 600;
  font-size: 0.85rem;
  border-radius: var(--radius-full);
  box-shadow: var(--shadow-sm);
  transition: transform var(--transition-fast), background-color var(--transition-fast), box-shadow var(--transition-fast);
}

.btn-whatsapp:hover {
  background-color: #128c7e;
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
}

/* Hamburger Menu button */
.hamburger-btn {
  display: none;
  flex-direction: column;
  justify-content: space-around;
  width: 24px;
  height: 20px;
  padding: 0;
}

.hamburger-line {
  width: 100%;
  height: 2px;
  background-color: var(--text-strong);
  border-radius: var(--radius-full);
  transition: all var(--transition-normal);
}

/* Mobile Nav Panel */
.mobile-nav-panel {
  position: fixed;
  top: 70px;
  left: 0;
  width: 100%;
  height: 0;
  background-color: var(--bg);
  border-bottom: 1px solid var(--border);
  overflow: hidden;
  transition: height var(--transition-normal);
}

.mobile-nav-panel.is-open {
  height: calc(100vh - 70px);
}

.mobile-nav {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 28px;
  height: 100%;
  padding-bottom: 100px;
}

.mobile-link {
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--text-strong);
  font-family: var(--font-heading);
}

.mobile-link:hover {
  color: var(--primary);
}

/* Responsive Breakpoints */
@media (max-width: 768px) {
  .desktop-nav {
    display: none;
  }
  
  .hamburger-btn {
    display: flex;
  }

  .open-top {
    transform: translateY(6px) rotate(45deg);
  }

  .open-mid {
    opacity: 0;
    transform: translateX(10px);
  }

  .open-bot {
    transform: translateY(-6px) rotate(-45deg);
  }

  .btn-whatsapp span {
    display: block;
  }
}
</style>
