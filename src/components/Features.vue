<script setup>
const features = [
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8"><path stroke-linecap="round" stroke-linejoin="round" d="M8.25 6.75h12M8.25 12h12m-12 5.25h12M3.75 6.75h.007v.008H3.75V6.75zm.375 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zM3.75 12h.007v.008H3.75V12zm.375 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm-.375 5.25h.007v.008H3.75v-.008zm.375 0a.375.375 0 11-.75 0 .375.375 0 01.75 0z" /></svg>`,
    title: "Stok Lengkap & Ready",
    description: "Menyediakan tabung gas LPG, kompor gas, regulator safety, rice cooker, blender, kipas angin, dan peralatan rumah tangga terlengkap."
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>`,
    title: "Coba Langsung di Toko",
    description: "Semua kompor gas dan barang elektronik dapat dicoba langsung di toko offline kami untuk memastikan semuanya berfungsi sempurna."
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75m-3-7.036A11.959 11.959 0 013.598 6 11.99 11.99 0 003 9.749c0 5.592 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.31-.21-2.571-.598-3.751A11.959 11.959 0 0112 2.25z" /></svg>`,
    title: "Standar SNI & Aman",
    description: "Semua peralatan gas (tabung gas LPG, regulator safety, selang) telah berstandar SNI demi keamanan maksimal dapur Anda."
  },
  {
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8"><path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z" /><path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z" /></svg>`,
    title: "Lokasi Mengwi Mudah Dijangkau",
    description: "Kunjungi toko offline kami di Bali untuk melihat produk secara langsung dan mendapatkan pelayanan langsung dari kami."
  }
];
</script>

<template>
  <section id="features" class="features-section">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header animate-on-scroll slide-up-fade">
        <h2 class="section-title">Mengapa Memilih <span class="text-gradient">Anom Elektronik & Gas</span>?</h2>
        <p class="section-subtitle">Kami berkomitmen memberikan pengalaman belanja barang elektronik terbaik dengan layanan unggulan.</p>
      </div>

      <!-- Features Grid -->
      <div class="features-grid">
        <div 
          v-for="(feature, index) in features" 
          :key="index" 
          :class="['feature-card', 'glass', 'glow-card', 'animate-on-scroll', 'slide-up-fade', 'delay-' + ((index + 1) * 100)]"
        >
          <div class="icon-box" v-html="feature.icon"></div>
          <h3 class="feature-card-title">{{ feature.title }}</h3>
          <p class="feature-card-desc">{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.features-section {
  padding: 100px 0;
  position: relative;
  background-color: var(--bg);
}

.section-header {
  text-align: center;
  max-width: 600px;
  margin: 0 auto 60px;
}

.section-title {
  font-size: clamp(2rem, 3.5vw, 2.6rem);
  font-weight: 800;
  letter-spacing: -1px;
  margin-bottom: 16px;
}

.section-subtitle {
  color: var(--text-muted);
  font-size: 1.05rem;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
}

.feature-card {
  padding: 40px 30px;
  border-radius: var(--radius-lg);
  text-align: left;
  transition: transform var(--transition-normal), box-shadow var(--transition-normal);
}

.icon-box {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 56px;
  height: 56px;
  border-radius: var(--radius-md);
  background-color: var(--border-glow);
  color: var(--primary);
  margin-bottom: 24px;
  border: 1px solid var(--border);
}

.feature-card:hover .icon-box {
  background-color: var(--primary);
  color: var(--text-white);
  border-color: transparent;
  transform: scale(1.05);
  transition: all var(--transition-normal);
}

.feature-card-title {
  font-size: 1.25rem;
  font-weight: 700;
  margin-bottom: 12px;
}

.feature-card-desc {
  color: var(--text-muted);
  font-size: 0.95rem;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .features-section {
    padding: 60px 0;
  }
  
  .feature-card {
    padding: 30px 24px;
  }
}
</style>
