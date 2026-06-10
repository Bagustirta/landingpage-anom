<script setup>
import { ref } from 'vue';

const formName = ref('');
const formEmail = ref('');
const formMessage = ref('');
const isSubmitted = ref(false);

const handleSubmit = () => {
  if (formName.value && formEmail.value && formMessage.value) {
    // Simulate API submission
    isSubmitted.value = true;
    setTimeout(() => {
      // Reset form
      formName.value = '';
      formEmail.value = '';
      formMessage.value = '';
      isSubmitted.value = false;
    }, 4000);
  }
};
</script>

<template>
  <section id="location" class="contact-section">
    <!-- Ambient glow lights behind content -->
    <div class="ambient-glow secondary-glow"></div>

    <div class="container contact-container">
      <!-- Left side: Contact details & Hours -->
      <div class="contact-info-col">
        <span class="info-badge">Kontak & Lokasi</span>
        <h2 class="section-title">Kunjungi <span class="text-gradient">Toko Kami</span></h2>
        <p class="section-subtitle">
          Kami siap menyambut Anda langsung di toko fisik kami untuk melihat dan mencoba produk secara langsung. Dapatkan rekomendasi terbaik dari tim ahli kami.
        </p>

        <!-- Details grid -->
        <div class="info-details-list">
          <div class="info-detail-item">
            <div class="info-icon-box">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1 1 15 0Z" />
              </svg>
            </div>
            <div class="info-text-box">
              <h4>Alamat Toko</h4>
              <p>Jl. Raya Kapal No.17 , Kec. Mengwi, Kabupaten Badung, Bali 80351</p>
            </div>
          </div>

          <div class="info-detail-item">
            <div class="info-icon-box">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
              </svg>
            </div>
            <div class="info-text-box">
              <h4>Jam Operasional</h4>
              <p>Senin - Sabtu: 09:00 - 21:00 WIB<br>Minggu & Hari Libur: 10:00 - 18:00 WIB</p>
            </div>
          </div>

          <div class="info-detail-item">
            <div class="info-icon-box">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 0 0 2.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-2.824-1.432-5.117-3.725-6.579-6.579l1.293-.97c.362-.272.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 0 0-1.091-.852H4.5A2.25 2.25 0 0 0 2.25 4.5v2.25Z" />
              </svg>
            </div>
            <div class="info-text-box">
              <h4>Kontak Customer Service</h4>
              <p>WhatsApp: +62 819-1384-2931<br>Email: support@anomelektronik.my.id</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Right side: Message form & Map -->
      <div class="contact-form-col">
        <div class="form-wrapper glass glow-card">
          <h3 class="form-title">Kirim Pertanyaan</h3>
          <p class="form-subtitle">Punya pertanyaan seputar ketersediaan stok atau klaim garansi? Hubungi kami langsung.</p>

          <!-- Form Element -->
          <form v-if="!isSubmitted" @submit.prevent="handleSubmit" class="message-form">
            <div class="form-group">
              <label for="name">Nama Lengkap</label>
              <input type="text" id="name" v-model="formName" placeholder="Contoh: Budi Santoso" required />
            </div>

            <div class="form-group">
              <label for="email">Alamat Email</label>
              <input type="email" id="email" v-model="formEmail" placeholder="Contoh: budi@gmail.com" required />
            </div>

            <div class="form-group">
              <label for="message">Pesan Anda</label>
              <textarea id="message" v-model="formMessage" rows="4" placeholder="Tuliskan pertanyaan Anda mengenai produk kami secara detail..." required></textarea>
            </div>

            <button type="submit" class="btn-submit">
              Kirim Pesan
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="btn-submit-icon" width="16" height="16">
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 12L3.269 3.126A59.768 59.768 0 0121.485 12 59.77 59.77 0 013.27 20.876L5.999 12zm0 0h7.5" />
              </svg>
            </button>
          </form>

          <!-- Success State -->
          <div v-else class="form-success-state">
            <div class="success-icon-box">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="w-10 h-10">
                <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12c0 1.268-.63 2.39-1.593 3.068a3.745 3.745 0 01-1.043 3.296 3.745 3.745 0 01-3.296 1.043A3.745 3.745 0 0112 21c-1.268 0-2.39-.63-3.068-1.593a3.746 3.746 0 01-3.296-1.043 3.745 3.745 0 01-1.043-3.296A3.745 3.745 0 013 12c0-1.268.63-2.39 1.593-3.068a3.745 3.745 0 011.043-3.296 3.746 3.746 0 013.296-1.043A3.746 3.746 0 0112 3c1.268 0 2.39.63 3.068 1.593a3.746 3.746 0 013.296 1.043 3.746 3.746 0 011.043 3.296A3.745 3.745 0 0121 12z" />
              </svg>
            </div>
            <h3>Pesan Terkirim!</h3>
            <p>Terima kasih telah menghubungi kami. Tim kami akan segera menanggapi email Anda dalam kurun waktu 1x24 jam.</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-section {
  padding: 100px 0;
  position: relative;
  overflow: hidden;
}

.ambient-glow {
  display: none;
}

.contact-container {
  display: grid;
  grid-template-columns: 1.1fr 1fr;
  gap: 60px;
  position: relative;
  z-index: 1;
}

.contact-info-col {
  text-align: left;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.info-badge {
  display: inline-flex;
  width: max-content;
  padding: 6px 14px;
  background-color: var(--border-glow);
  border: 1px solid var(--border);
  color: var(--primary);
  font-weight: 600;
  font-size: 0.85rem;
  border-radius: var(--radius-full);
  margin-bottom: 20px;
}

.section-title {
  font-size: clamp(2rem, 3.5vw, 2.6rem);
  font-weight: 800;
  letter-spacing: -1px;
  margin-bottom: 20px;
}

.section-subtitle {
  color: var(--text-muted);
  font-size: 1.05rem;
  margin-bottom: 40px;
}

.info-details-list {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.info-detail-item {
  display: flex;
  gap: 20px;
  align-items: flex-start;
}

.info-icon-box {
  width: 48px;
  height: 48px;
  border-radius: var(--radius-md);
  background-color: var(--border-glow);
  color: var(--primary);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  border: 1px solid var(--border);
}

.info-icon-box svg {
  width: 24px;
  height: 24px;
  flex-shrink: 0;
}

.info-text-box h4 {
  font-size: 1.1rem;
  font-weight: 700;
  margin-bottom: 6px;
}

.info-text-box p {
  color: var(--text-muted);
  font-size: 0.95rem;
  line-height: 1.5;
}

/* Contact Form column styles */
.contact-form-col {
  display: flex;
  align-items: center;
}

.form-wrapper {
  width: 100%;
  padding: 40px;
  border-radius: var(--radius-lg);
  text-align: left;
}

.form-title {
  font-size: 1.4rem;
  font-weight: 700;
  margin-bottom: 8px;
}

.form-subtitle {
  color: var(--text-muted);
  font-size: 0.88rem;
  margin-bottom: 28px;
  line-height: 1.4;
}

.message-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.form-group label {
  font-size: 0.85rem;
  font-weight: 600;
  color: var(--text-strong);
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 12px 16px;
  background-color: var(--bg);
  border: 1px solid var(--border);
  color: var(--text-strong);
  font-size: 0.9rem;
  border-radius: var(--radius-sm);
  transition: all var(--transition-fast);
}

.form-group input:focus,
.form-group textarea:focus {
  border-color: var(--primary);
  box-shadow: 0 0 0 3px var(--border-glow);
}

.btn-submit {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  padding: 8px 20px;
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  color: var(--text-white);
  font-weight: 600;
  font-size: 0.85rem;
  border-radius: var(--radius-full);
  box-shadow: var(--shadow-sm);
  margin-top: 10px;
  align-self: flex-start;
  transition: all var(--transition-fast);
}

.btn-submit:hover {
  opacity: 0.95;
  transform: translateY(-1px);
  box-shadow: var(--shadow-md);
}

.btn-submit-icon {
  width: 16px;
  height: 16px;
  flex-shrink: 0;
}

/* Success layout */
.form-success-state {
  text-align: center;
  padding: 40px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.success-icon-box {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  background-color: rgba(16, 185, 129, 0.1);
  color: #10b981;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 24px;
  animation: pulse-glow 2s infinite;
}

.form-success-state h3 {
  font-size: 1.5rem;
  margin-bottom: 12px;
}

.form-success-state p {
  color: var(--text-muted);
  font-size: 0.95rem;
  line-height: 1.6;
}

/* Responsive styles */
@media (max-width: 992px) {
  .contact-container {
    grid-template-columns: 1fr;
    gap: 50px;
  }
  
  .contact-info-col {
    text-align: center;
    align-items: center;
  }

  .section-subtitle {
    margin-inline: auto;
  }
}

@media (max-width: 480px) {
  .form-wrapper {
    padding: 24px;
  }
}
</style>
