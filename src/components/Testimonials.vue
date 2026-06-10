<template>
  <section id="testimonials" class="testimonials-section">
    <div class="ambient-glow accent-glow"></div>
    <div class="container">
      <div class="section-header">
        <span class="badge">Ulasan Pelanggan</span>
        <h2 class="section-title">Apa Kata <span class="text-gradient">Mereka?</span></h2>
        <p class="section-subtitle">Dukungan kepercayaan dari para tetangga dan pelaku usaha kuliner di Bali.</p>
      </div>

      <div class="testimonials-grid">
        <div class="testimonial-card glass glow-card">
          <div class="rating">
            <span v-for="n in 5" :key="n" class="star">★</span>
          </div>
          <p class="testimonial-text">
            "Layanan antar gas LPG-nya luar biasa cepat. Cukup WA langsung diantar ke rumah kurang dari 20 menit dan dibantu dipasang sekalian dengan aman. Sangat direkomendasikan!"
          </p>
          <div class="user-info">
            <div class="avatar-box color-1">B</div>
            <div>
              <h4 class="user-name">Pak Bambang</h4>
              <span class="user-role">Rumah Tangga - Kapal, Mengwi</span>
            </div>
          </div>
        </div>

        <div class="testimonial-card glass glow-card">
          <div class="rating">
            <span v-for="n in 5" :key="n" class="star">★</span>
          </div>
          <p class="testimonial-text">
            "Beli penanak nasi Miyako dan kipas Maspion di sini harganya sangat terjangkau. Yang paling penting, barangnya bisa dites langsung di toko jadi terjamin nyala dan berfungsi."
          </p>
          <div class="user-info">
            <div class="avatar-box color-2">S</div>
            <div>
              <h4 class="user-name">Ibu Sri Wahyuni</h4>
              <span class="user-role">Ibu Rumah Tangga - Dharmahusada</span>
            </div>
          </div>
        </div>

        <div class="testimonial-card glass glow-card">
          <div class="rating">
            <span v-for="n in 5" :key="n" class="star">★</span>
          </div>
          <p class="testimonial-text">
            "Langganan isi ulang gas melon 3 kg untuk warung makan saya. Layanan cepat, segel gas resmi Pertamina utuh, aman, dan pelayanannya ramah sekali."
          </p>
          <div class="user-info">
            <div class="avatar-box color-3">H</div>
            <div>
              <h4 class="user-name">Mas Hendra</h4>
              <span class="user-role">Pemilik Warung Makan - Mengwi, Badung</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.testimonials-section {
  padding: 100px 0;
  position: relative;
  background-color: var(--bg);
}

.badge {
  display: inline-block;
  padding: 6px 14px;
  background: rgba(255, 107, 0, 0.1);
  color: var(--primary);
  border: 1.5px solid rgba(255, 107, 0, 0.2);
  border-radius: var(--radius-full);
  font-size: 0.8rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 16px;
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

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  position: relative;
  z-index: 1;
}

.testimonial-card {
  padding: 30px;
  border-radius: var(--radius-lg);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.rating {
  margin-bottom: 16px;
  display: flex;
  gap: 4px;
}

.star {
  color: #ffb800;
  font-size: 1.2rem;
}

.testimonial-text {
  font-size: 0.95rem;
  line-height: 1.6;
  color: var(--text);
  margin-bottom: 24px;
  font-style: italic;
}

.user-info {
  display: flex;
  align-items: center;
  gap: 14px;
}

.avatar-box {
  width: 44px;
  height: 44px;
  border-radius: var(--radius-full);
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  color: #ffffff;
  font-size: 1.1rem;
}

/* Beautiful distinct avatar colors to make it colorful! */
.color-1 {
  background: linear-gradient(135deg, #ff6b00, #ff9f43);
}

.color-2 {
  background: linear-gradient(135deg, #00d2ff, #0082ff);
}

.color-3 {
  background: linear-gradient(135deg, #9d4edd, #c77dff);
}

.user-name {
  font-size: 1rem;
  font-weight: 700;
  color: var(--text-strong);
}

.user-role {
  font-size: 0.78rem;
  color: var(--text-muted);
}

/* Responsive Layout */
@media (max-width: 1024px) {
  .testimonials-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 24px;
  }
}

@media (max-width: 640px) {
  .testimonials-grid {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  
  .testimonial-card {
    padding: 24px;
  }
}
</style>
