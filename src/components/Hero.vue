<script setup>
// Hero component logic
</script>

<template>
  <section id="hero" class="hero-section">
    <!-- Ambient glow lights for colorful premium design -->
    <div class="ambient-glow primary-glow" style="top: 10%; left: -100px;"></div>
    <div class="ambient-glow secondary-glow" style="bottom: 10%; right: -100px;"></div>

    <!-- Wavy divider SVG at the bottom of Hero -->
    <div class="hero-wave">
      <svg viewBox="0 0 1440 120" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
        <path d="M0,0 C320,80 720,120 1440,0 L1440,120 L0,120 Z" fill="var(--bg)"></path>
      </svg>
    </div>

    <div class="container hero-container">
      <!-- Hero Copywriting -->
      <div class="hero-content animate-slide-up">
        <h1 class="hero-title">
          Penyedia Elektronik, Kompor & <span class="text-gradient">Gas LPG Terpercaya</span>
        </h1>
        <p class="hero-subtitle">
          Pusat penjualan tabung gas LPG, kompor, regulator safety, dan alat elektronik rumah tangga terlengkap di Mengwi, Bali. Kunjungi toko fisik kami untuk melihat pilihan produk secara langsung.
        </p>

        <!-- Bullet Highlights -->
        <div class="hero-bullets">
          <div class="bullet-item">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="w-5 h-5 check-icon">
              <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
            </svg>
            <span>Layanan Gas LPG 3kg (Gas Melon)</span>
          </div>
          <div class="bullet-item">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="w-5 h-5 check-icon">
              <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
            </svg>
            <span>Kompor & Alat Masak</span>
          </div>
          <div class="bullet-item">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="w-5 h-5 check-icon">
              <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
            </svg>
            <span>Elektronik Rumah Tangga</span>
          </div>
        </div>

        <!-- Call to Actions -->
        <div class="hero-actions">
          <a href="#catalog" class="btn-primary">
            Pilihan Produk
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5 arrow-icon">
              <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3" />
            </svg>
          </a>
          <a href="https://wa.me/6281913842931?text=Halo%20Anom%20Elektronik%2C%20saya%20ingin%20tanya%20stok%20barang%20dan%20lokasi%20toko%20offline%20Anda." target="_blank" rel="noopener noreferrer" class="btn-secondary">
            Tanya Admin
          </a>
        </div>
      </div>

      <!-- Hero Visual Image -->
      <div class="hero-visual">
        <!-- Organic Morphing Curved Background Shapes behind the image -->
        <div class="curve-bg-1"></div>
        <div class="curve-bg-2"></div>
        
        <div class="image-wrapper">
          <img src="/images/hero_localized_electronics_v3.png" alt="Premium Electronics Anom" class="hero-img animate-float" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding-top: 100px;
  padding-bottom: 140px;
  background-color: var(--bg);
  overflow: hidden;
}

.hero-container {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 48px;
  align-items: center;
  position: relative;
  z-index: 1;
}

.hero-content {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  text-align: left;
}

.badge-store {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 14px;
  background-color: var(--border-glow);
  border: 1px solid var(--border);
  color: var(--primary);
  font-weight: 600;
  font-size: 0.85rem;
  border-radius: var(--radius-full);
  margin-bottom: 24px;
}

.pulse-dot {
  width: 8px;
  height: 8px;
  background-color: var(--primary);
  border-radius: 50%;
  position: relative;
}

.pulse-dot::after {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: 50%;
  background-color: var(--primary);
  animation: pulse-glow 1.5s infinite;
  transform: scale(2);
  opacity: 0.5;
}

.hero-title {
  font-size: clamp(2.5rem, 4vw, 3.8rem);
  line-height: 1.15;
  font-weight: 800;
  letter-spacing: -1.5px;
  margin-bottom: 20px;
}

.hero-subtitle {
  font-size: 1.1rem;
  color: var(--text-muted);
  margin-bottom: 30px;
  max-width: 540px;
}

.hero-bullets {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-bottom: 35px;
}

.bullet-item {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.95rem;
  font-weight: 500;
  color: var(--text);
}

.check-icon {
  width: 18px;
  height: 18px;
  color: var(--primary);
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}

.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 24px;
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  color: var(--text-white);
  font-weight: 600;
  font-size: 0.9rem;
  border-radius: var(--radius-full);
  box-shadow: var(--shadow-sm);
  transition: transform var(--transition-fast), opacity var(--transition-fast), box-shadow var(--transition-fast);
}

.btn-primary:hover {
  opacity: 0.95;
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
}

.arrow-icon {
  width: 16px;
  height: 16px;
  transition: transform var(--transition-fast);
}

.btn-primary:hover .arrow-icon {
  transform: translateX(4px);
}

.btn-secondary {
  padding: 10px 24px;
  background-color: var(--bg-card);
  border: 1px solid var(--border);
  color: var(--text-strong);
  font-weight: 600;
  font-size: 0.9rem;
  border-radius: var(--radius-full);
  transition: background-color var(--transition-fast), border-color var(--transition-fast), transform var(--transition-fast);
}

.btn-secondary:hover {
  background-color: var(--border);
  border-color: var(--text-muted);
  transform: translateY(-1px);
}

.hero-wave {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100px;
  line-height: 0;
  z-index: 2;
  pointer-events: none;
}

.hero-wave svg {
  width: 100%;
  height: 100%;
  display: block;
}

/* Right Section Image Visual */
.hero-visual {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 40px 0;
}

/* Organic curved background shapes - "lengkung-lengkung" meta design */
.curve-bg-1 {
  position: absolute;
  width: 100%;
  max-width: 440px;
  height: 440px;
  background: linear-gradient(135deg, #ffe8d6 0%, #ffcca8 100%);
  border-radius: 43% 57% 38% 62% / 55% 43% 57% 45%;
  z-index: 0;
  animation: morph 8s ease-in-out infinite;
  opacity: 0.7;
}

.curve-bg-2 {
  position: absolute;
  width: 100%;
  max-width: 400px;
  height: 400px;
  background: linear-gradient(135deg, var(--primary-light) 0%, var(--primary) 100%);
  border-radius: 50% 50% 30% 70% / 50% 60% 40% 60%;
  z-index: 1;
  opacity: 0.15;
  animation: morph-reverse 10s ease-in-out infinite;
}

.image-wrapper {
  position: relative;
  z-index: 2;
  transition: transform var(--transition-normal);
}

.image-wrapper:hover {
  transform: scale(1.05);
}

.hero-img {
  width: 100%;
  max-width: 420px;
  height: auto;
  display: block;
  filter: drop-shadow(0 15px 30px rgba(15, 23, 42, 0.12));
}

@keyframes morph {
  0% {
    border-radius: 42% 58% 70% 30% / 45% 45% 55% 55%;
  }
  50% {
    border-radius: 70% 30% 52% 48% / 60% 40% 60% 40%;
  }
  100% {
    border-radius: 42% 58% 70% 30% / 45% 45% 55% 55%;
  }
}

@keyframes morph-reverse {
  0% {
    border-radius: 50% 50% 30% 70% / 50% 60% 40% 60%;
  }
  50% {
    border-radius: 30% 70% 70% 30% / 50% 30% 70% 50%;
  }
  100% {
    border-radius: 50% 50% 30% 70% / 50% 60% 40% 60%;
  }
}

/* Responsive Styles */
@media (max-width: 992px) {
  .hero-container {
    grid-template-columns: 1fr;
    gap: 40px;
    text-align: center;
  }

  .hero-content {
    align-items: center;
    text-align: center;
  }

  .hero-subtitle {
    margin-inline: auto;
  }

  .hero-bullets {
    justify-content: center;
  }

  .hero-actions {
    justify-content: center;
  }

  .hero-visual {
    margin-top: 20px;
    max-width: 440px;
    margin-inline: auto;
  }
}
</style>
