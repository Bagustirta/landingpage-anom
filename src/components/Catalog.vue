<script setup>
const categories = [
  {
    title: "Tabung Gas LPG",
    description: "Penyedia resmi isi ulang dan tabung baru gas LPG Pertamina 3 kg (gas melon) untuk rumah tangga maupun usaha.",
    examples: ["Tabung Melon 3 Kg", "Isi Ulang Gas 3 Kg", "Layanan Tukar Tabung", "Aksesoris Selang & Regulator"],
    iconClass: "icon-gas"
  },
  {
    title: "Kompor Gas & Regulator",
    description: "Peralatan kompor gas aman dan regulator berstandar SNI demi keamanan maksimal dapur Anda.",
    examples: ["Kompor Gas 1 & 2 Tungku", "Regulator Gas Safety", "Selang Metal Safety", "Aksesoris Kompor"],
    iconClass: "icon-stove"
  },
  {
    title: "Elektronik Dapur",
    description: "Peralatan dapur bertenaga listrik yang membantu mempermudah proses memasak sehari-hari.",
    examples: ["Rice Cooker / Penanak Nasi", "Blender & Chopper", "Dispenser Air Panas/Dingin", "Mixer Serbaguna"],
    iconClass: "icon-kitchen"
  },
  {
    title: "Kipas Angin & Pendingin",
    description: "Berbagai tipe kipas angin berkualitas untuk sirkulasi udara rumah yang lebih sejuk.",
    examples: ["Kipas Meja & Dinding", "Kipas Berdiri (Stand Fan)", "Exhaust Fan Ventilasi", "Kipas Angin Karakter"],
    iconClass: "icon-fan"
  },
  {
    title: "Elektronik Rumah Tangga",
    description: "Peralatan elektronik penunjang kenyamanan dan kebutuhan listrik rumah tangga Anda.",
    examples: ["Setrika Listrik", "Lampu LED Hemat Energi", "Kabel Roll & Stopkontak", "Set Top Box & Antena TV"],
    iconClass: "icon-household"
  }
];
</script>

<template>
  <section id="catalog" class="catalog-section">
    <div class="container">
      <!-- Section Header -->
      <div class="section-header animate-on-scroll slide-up-fade">
        <h2 class="section-title">Barang Yang <span class="text-gradient">Kami Sediakan</span></h2>
        <p class="section-subtitle">Kami menjual berbagai macam kebutuhan rumah tangga, peralatan gas, dan alat elektronik secara offline.</p>
      </div>

      <!-- Categories Grid -->
      <div class="categories-grid">
        <div 
          v-for="(cat, index) in categories" 
          :key="index" 
          :class="['category-card', 'glass', 'glow-card', 'animate-on-scroll', 'slide-up-fade', 'delay-' + ((index + 1) * 100)]"
        >
          <div class="category-header">
            <!-- Illustrative Icons -->
            <div :class="['category-icon-box', cat.iconClass]">
              <!-- Tabung Gas LPG Icon -->
              <svg v-if="cat.iconClass === 'icon-gas'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="icon-svg">
                <path stroke-linecap="round" stroke-linejoin="round" d="M15.362 5.214A8.252 8.252 0 0 1 12 21 8.25 8.25 0 0 1 6.038 7.047 8.287 8.287 0 0 0 9 9.601a8.983 8.983 0 0 1 3.361-6.867 8.21 8.21 0 0 0 3 2.48Z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 18a3.75 3.75 0 0 0 .495-7.467 5.99 5.99 0 0 0-1.925 3.546 5.974 5.974 0 0 1 2.133-1.881A3.75 3.75 0 0 0 12 18Z" />
              </svg>
              <!-- Kompor Gas Icon -->
              <svg v-else-if="cat.iconClass === 'icon-stove'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="icon-svg">
                <path stroke-linecap="round" stroke-linejoin="round" d="M15.362 5.214A8.252 8.252 0 0 1 12 21 8.25 8.25 0 0 1 6.038 7.047 8.287 8.287 0 0 0 9 9.601a8.983 8.983 0 0 1 3.361-6.867 8.21 8.21 0 0 0 3 2.48Z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 2.25V5.25M12 18.75V21.75M5.25 12H2.25M21.75 12H18.75" />
              </svg>
              <!-- Elektronik Dapur Icon -->
              <svg v-else-if="cat.iconClass === 'icon-kitchen'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="icon-svg">
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 6.042A8.967 8.967 0 0 0 6 3.75c-1.052 0-2.062.18-3 .512v14.25A8.987 8.987 0 0 1 6 18c2.305 0 4.408.867 6 2.292m0-16.25a8.966 8.966 0 0 1 6-2.292c1.052 0 2.062.18 3 .512v14.25A8.987 8.987 0 0 0 18 18a8.967 8.967 0 0 0-6 2.292m0-16.25v16.25" />
              </svg>
              <!-- Kipas Angin Icon -->
              <svg v-else-if="cat.iconClass === 'icon-fan'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="icon-svg">
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 12a6 6 0 0 1 12 0v6a6 6 0 0 1-12 0v-6Z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 6V3m0 18v-3M6 12H3m18 0h-3" />
              </svg>
              <!-- Elektronik RT Icon -->
              <svg v-else-if="cat.iconClass === 'icon-household'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="icon-svg">
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 22.5h12a2.25 2.25 0 0 0 2.25-2.25V6.75A2.25 2.25 0 0 0 18 4.5H6a2.25 2.25 0 0 0-2.25 2.25v13.5A2.25 2.25 0 0 0 6 22.5Z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 18.75a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z" />
              </svg>
              <!-- Kelontong Icon -->
              <svg v-else xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="icon-svg">
                <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 0 0-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 0 0-16.536-1.84M7.5 14.25L5.106 5.272M6 20.25a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Zm12.75 0a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Z" />
              </svg>
            </div>
            <h3 class="category-title">{{ cat.title }}</h3>
          </div>
          
          <p class="category-desc">{{ cat.description }}</p>
          
          <div class="examples-divider"></div>
          
          <div class="category-examples">
            <h4 class="examples-title">Menyediakan antara lain:</h4>
            <ul class="examples-list">
              <li v-for="(ex, idx) in cat.examples" :key="idx" class="example-item">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="3" stroke="currentColor" class="check-icon">
                  <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                </svg>
                <span>{{ ex }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.catalog-section {
  padding: 100px 0;
  position: relative;
  background-color: var(--bg-alt);
}

.section-header {
  text-align: center;
  max-width: 700px;
  margin: 0 auto 60px;
}

.section-title {
  font-size: clamp(2rem, 3.5vw, 2.6rem);
  font-weight: 800;
  letter-spacing: -1px;
  margin-bottom: 16px;
}

.section-subtitle {
  font-size: clamp(0.95rem, 1.2vw, 1.1rem);
  color: var(--text-muted);
  line-height: 1.6;
}

.categories-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 30px;
}

.category-card {
  width: calc(33.333% - 20px);
  min-width: 320px;
  padding: 30px;
  border-radius: var(--radius-lg);
  display: flex;
  flex-direction: column;
  transition: transform var(--transition-normal), box-shadow var(--transition-normal);
}

.category-card:hover {
  transform: translateY(-5px);
}

.category-header {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 20px;
}

.category-icon-box {
  width: 50px;
  height: 50px;
  border-radius: var(--radius-md);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.icon-svg {
  width: 26px;
  height: 26px;
}

/* Color codes for specific category icons */
.icon-gas {
  background-color: rgba(16, 185, 129, 0.1);
  color: #10b981;
  border: 1px solid rgba(16, 185, 129, 0.2);
}

.icon-stove {
  background-color: rgba(245, 158, 11, 0.1);
  color: #f59e0b;
  border: 1px solid rgba(245, 158, 11, 0.2);
}

.icon-kitchen {
  background-color: rgba(59, 130, 246, 0.1);
  color: #3b82f6;
  border: 1px solid rgba(59, 130, 246, 0.2);
}

.icon-fan {
  background-color: rgba(139, 92, 246, 0.1);
  color: #8b5cf6;
  border: 1px solid rgba(139, 92, 246, 0.2);
}

.icon-household {
  background-color: rgba(236, 72, 153, 0.1);
  color: #ec4899;
  border: 1px solid rgba(236, 72, 153, 0.2);
}

.icon-grocery {
  background-color: rgba(20, 184, 166, 0.1);
  color: #14b8a6;
  border: 1px solid rgba(20, 184, 166, 0.2);
}

.category-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--text-strong);
}

.category-desc {
  font-size: 0.9rem;
  color: var(--text-muted);
  line-height: 1.6;
  margin-bottom: 24px;
  flex-grow: 1;
}

.examples-divider {
  height: 1px;
  background-color: var(--border);
  margin-bottom: 20px;
  width: 100%;
}

.category-examples {
  margin-top: auto;
}

.examples-title {
  font-size: 0.85rem;
  font-weight: 700;
  color: var(--text-strong);
  margin-bottom: 12px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.examples-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.example-item {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 0.88rem;
  color: var(--text);
}

.check-icon {
  width: 14px;
  height: 14px;
  color: var(--primary);
  flex-shrink: 0;
}

/* Responsive Grid */
@media (max-width: 1024px) {
  .category-card {
    width: calc(50% - 15px);
    min-width: 280px;
  }
}

@media (max-width: 640px) {
  .category-card {
    width: 100%;
    padding: 24px;
  }
}
</style>
