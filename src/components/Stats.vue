<template>
  <section class="stats-section">
    <div class="container">
      <div class="stats-grid">
        <div class="stat-card glass glow-card">
          <div class="stat-number">10+</div>
          <div class="stat-label">Tahun Pengalaman</div>
          <p class="stat-desc">Melayani pasokan gas dan alat rumah tangga terpercaya sejak 2016.</p>
        </div>
        
        <div class="stat-card glass glow-card">
          <div class="stat-number">5.000+</div>
          <div class="stat-label">Pelanggan Setia</div>
          <p class="stat-desc">Dipercaya oleh ribuan keluarga dan usaha kuliner di wilayah Mengwi & sekitarnya.</p>
        </div>

        <div class="stat-card glass glow-card">
          <div class="stat-number">100%</div>
          <div class="stat-label">Keamanan SNI</div>
          <p class="stat-desc">Semua tabung gas, regulator, dan elektronik dapur dijamin orisinal dan bersertifikasi.</p>
        </div>

        <div class="stat-card glass glow-card">
          <div class="stat-number">&lt; 30 Mnt</div>
          <div class="stat-label">Layanan Antar Cepat</div>
          <p class="stat-desc">Layanan pengiriman tabung gas LPG langsung dipasang ke rumah Anda dengan aman.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.stats-section {
  padding: 60px 0;
  position: relative;
  background-color: var(--bg-alt);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 30px;
}

.stat-card {
  padding: 30px;
  border-radius: var(--radius-lg);
  text-align: center;
  position: relative;
  overflow: hidden;
}

.stat-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: linear-gradient(90deg, var(--primary), var(--primary-light));
}

.stat-number {
  font-size: clamp(2.2rem, 3.5vw, 3rem);
  font-weight: 800;
  background: linear-gradient(135deg, var(--primary), #ff9f43);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 8px;
  font-family: var(--font-heading);
}

.stat-label {
  font-size: 1.05rem;
  font-weight: 700;
  color: var(--text-strong);
  margin-bottom: 10px;
}

.stat-desc {
  font-size: 0.85rem;
  color: var(--text-muted);
  line-height: 1.5;
}

/* Responsive Layout */
@media (max-width: 1024px) {
  .stats-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 24px;
  }
}

@media (max-width: 640px) {
  .stats-grid {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  
  .stat-card {
    padding: 24px;
  }
}
</style>
