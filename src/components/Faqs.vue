<script setup>
import { ref } from 'vue';

const faqs = ref([
  {
    question: "Apakah tabung gas LPG dijamin aman dan asli?",
    answer: "Ya, 100% dijamin aman dan asli Pertamina. Semua pasokan gas LPG kami berasal langsung dari SPBE resmi Pertamina, dengan segel plastik utuh (seal cap) dan karet pelindung (rubber valve) standar keselamatan.",
    open: false
  },
  {
    question: "Bagaimana cara memesan layanan antar gas ke rumah?",
    answer: "Sangat mudah! Hubungi kami melalui WhatsApp di tombol 'Tanya Stok' atau 'Tanya Admin'. Kirimkan nama, jenis tabung gas, dan alamat lengkap Anda. Kurir kami siap mengantar dan memasangkannya langsung di dapur Anda.",
    open: false
  },
  {
    question: "Apakah barang elektronik dapur & rumah tangga bergaransi?",
    answer: "Tentu saja. Seluruh produk elektronik yang kami jual (seperti Maspion, Miyako, Cosmos, dll.) bergaransi resmi pabrik. Sebelum dibawa pulang, barang wajib diuji/dites kelayakannya di toko bersama tim kami.",
    open: false
  },
  {
    question: "Apakah melayani pembayaran non-tunai (QRIS)?",
    answer: "Ya! Kami melayani pembayaran tunai maupun non-tunai via QRIS (seperti GoPay, OVO, Dana, LinkAja, ShopeePay, serta Mobile Banking) untuk transaksi yang lebih mudah dan aman di toko fisik.",
    open: false
  },
  {
    question: "Di mana alamat lengkap dan jam buka toko?",
    answer: "Toko kami berlokasi di Jl. Raya Kapal No. 17, Kecamatan Mengwi, Kabupaten Badung, Bali. Buka setiap hari Senin hingga Sabtu jam 09:00 - 21:00 WITA, dan Minggu jam 10:00 - 18:00 WITA.",
    open: false
  }
]);

const toggleFaq = (index) => {
  faqs.value[index].open = !faqs.value[index].open;
};
</script>

<template>
  <section id="faqs" class="faqs-section">
    <div class="ambient-glow primary-glow"></div>
    <div class="container">
      <div class="section-header">
        <span class="badge">Tanya Jawab</span>
        <h2 class="section-title">Pertanyaan <span class="text-gradient">Umum (FAQ)</span></h2>
        <p class="section-subtitle">Jawaban cepat seputar keamanan produk, layanan antar, dan operasional toko kami.</p>
      </div>

      <div class="faqs-list">
        <div 
          v-for="(faq, index) in faqs" 
          :key="index" 
          class="faq-item glass"
          :class="{ active: faq.open }"
        >
          <button class="faq-question-btn" @click="toggleFaq(index)" :aria-expanded="faq.open">
            <span class="question-text">{{ faq.question }}</span>
            <span class="faq-icon-box">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="faq-chevron">
                <path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
              </svg>
            </span>
          </button>
          
          <div class="faq-answer-wrapper" :style="{ maxHeight: faq.open ? '200px' : '0' }">
            <p class="faq-answer-text">{{ faq.answer }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.faqs-section {
  padding: 100px 0;
  position: relative;
  background-color: var(--bg-alt);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
}

.badge {
  display: inline-block;
  padding: 6px 14px;
  background: rgba(249, 90, 2, 0.08);
  color: var(--primary);
  border: 1.5px solid rgba(249, 90, 2, 0.15);
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

.faqs-list {
  max-width: 800px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 16px;
  position: relative;
  z-index: 1;
}

.faq-item {
  border-radius: var(--radius-md);
  overflow: hidden;
  transition: all var(--transition-normal);
}

.faq-item:hover {
  border-color: var(--primary);
  box-shadow: var(--shadow-md);
}

.faq-item.active {
  border-color: var(--primary);
  box-shadow: var(--shadow-md);
  background: #fffcfb;
}

.faq-question-btn {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 24px 30px;
  text-align: left;
  font-weight: 700;
  color: var(--text-strong);
  font-size: 1.05rem;
  transition: color var(--transition-fast);
}

.faq-question-btn:hover {
  color: var(--secondary);
}

.faq-icon-box {
  width: 32px;
  height: 32px;
  border-radius: var(--radius-full);
  background: rgba(0, 0, 0, 0.04);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all var(--transition-fast);
}

.faq-chevron {
  width: 16px;
  height: 16px;
  color: var(--text-muted);
  transition: transform var(--transition-normal);
}

.faq-item.active .faq-chevron {
  transform: rotate(180deg);
  color: var(--primary);
}

.faq-item.active .faq-icon-box {
  background: rgba(255, 107, 0, 0.1);
}

.faq-answer-wrapper {
  transition: max-height var(--transition-normal) ease-in-out;
  overflow: hidden;
}

.faq-answer-text {
  padding: 0 30px 24px;
  font-size: 0.92rem;
  color: var(--text);
  line-height: 1.7;
}

/* Responsive Layout */
@media (max-width: 640px) {
  .faq-question-btn {
    padding: 18px 20px;
    font-size: 0.95rem;
  }
  
  .faq-answer-text {
    padding: 0 20px 18px;
    font-size: 0.88rem;
  }
}
</style>
