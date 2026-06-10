<script setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="footer-wrapper glass">
    <div class="container footer-container">
      <!-- Info Column -->
      <div class="footer-info-col">
        <a href="#" class="footer-logo">
          <img src="/images/anom_logo.webp" alt="Anom Logo" class="logo-img" />
          <span class="logo-text">Anom<span class="highlight">Elektronik & Gas</span></span>
        </a>
        <p class="footer-desc">
          Pusat penyedia tabung gas LPG resmi Pertamina, kompor gas standar SNI, serta peralatan elektronik rumah tangga berkualitas tinggi di Bali.
        </p>
      </div>

      <!-- Links Column 1 -->
      <div class="footer-links-col">
        <h4>Navigasi</h4>
        <ul class="footer-links">
          <li><a href="#hero">Beranda</a></li>
          <li><a href="#catalog">Katalog</a></li>
          <li><a href="#features">Keunggulan</a></li>
          <li><a href="#location">Lokasi Toko</a></li>
        </ul>
      </div>

      <!-- Links Column 2 -->
      <div class="footer-links-col">
        <h4>Layanan Kami</h4>
        <ul class="footer-links">
          <li><a href="#catalog">Tabung Gas LPG</a></li>
          <li><a href="#catalog">Kompor & Regulator</a></li>
          <li><a href="#catalog">Elektronik Dapur</a></li>
          <li><a href="#catalog">Alat Rumah Tangga</a></li>
        </ul>
      </div>

      <!-- Links Column 3 (Socials) -->
      <div class="footer-links-col">
        <h4>Ikuti Kami</h4>
        <div class="social-row">
          <!-- Facebook -->
          <a href="#" class="social-icon-box" aria-label="Facebook">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" class="bi bi-facebook" viewBox="0 0 16 16">
              <path d="M16 8.049c0-4.446-3.582-8.05-8-8.05C3.58 0-.002 3.603-.002 8.05c0 4.017 2.926 7.347 6.75 7.951v-5.625h-2.03V8.05H6.75V6.275c0-2.017 1.195-3.131 3.022-3.131.876 0 1.791.157 1.791.157v1.98h-1.009c-.993 0-1.303.621-1.303 1.258v1.51h2.218l-.354 2.326H9.25V16c3.824-.604 6.75-3.934 6.75-7.951z"/>
            </svg>
          </a>
          <!-- Instagram -->
          <a href="#" class="social-icon-box" aria-label="Instagram">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" class="bi bi-instagram" viewBox="0 0 16 16">
              <path d="M8 0C5.829 0 5.556.01 4.703.048 3.85.088 3.269.222 2.76.42a3.917 3.917 0 0 0-1.417.923A3.927 3.927 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297.04.852.174 1.433.372 1.942.205.526.478.972.923 1.417.444.445.89.719 1.416.923.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.916 3.916 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.926 3.926 0 0 0-.923-1.417A3.911 3.911 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.999 0h.002zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046.78.035 1.204.166 1.486.275.373.145.64.319.92.599.28.28.453.546.598.92.11.281.24.705.275 1.485.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.47 2.47 0 0 1-.599.919c-.28.28-.546.453-.92.598-.28.11-.704.24-1.485.276-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.478 2.478 0 0 1-.92-.598 2.48 2.48 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485-.038-.843-.046-1.096-.046-3.233 0-2.136.008-2.388.046-3.231.036-.78.166-1.204.276-1.486.145-.373.319-.64.599-.92.28-.28.546-.453.92-.598.282-.11.705-.24 1.485-.276.738-.034 1.024-.044 2.515-.045v.002zm4.988 1.328a.96.96 0 1 0 0 1.92.96.96 0 0 0 0-1.92zm-4.27 1.122a4.109 4.109 0 1 0 0 8.217 4.109 4.109 0 0 0 0-8.217zm0 1.441a2.667 2.667 0 1 1 0 5.334 2.667 2.667 0 0 1 0-5.334z"/>
            </svg>
          </a>
          <!-- YouTube -->
          <a href="#" class="social-icon-box" aria-label="YouTube">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" class="bi bi-youtube" viewBox="0 0 16 16">
              <path d="M8.051 1.999h.089c.822.003 4.987.033 6.11.335a2.01 2.01 0 0 1 1.415 1.42c.101.38.172.883.22 1.402l.01.104.022.26.008.104c.065.914.073 1.77.074 1.957v.075c-.001.194-.01 1.108-.104 1.981l-.062.513c-.048.518-.12.1-.22.1.22.102-.38.173-.883.22l-.104.01-.26.022-.104.008c-.914.065-1.77.073-1.957.074H8.07c-.193-.001-1.109-.01-1.981-.104l-.513-.062c-.518-.048-1.006-.12-1.403-.22l-.104-.01-.26-.022-.104-.008c-.914-.065-1.77-.073-1.957-.074H5.93c-.193 0-1.108-.008-1.98-.103l-.514-.062a15.753 15.753 0 0 1-1.402-.22l-.104-.01-.26-.022-.104-.008C.893 10.48 0 8.01 0 8.01a80.6 80.6 0 0 1-.004-.847v-.076c.004-.194.01-1.108.104-1.981l.062-.513C.215 4.1.287 3.597.388 3.199c.102-.397.38-.883.882-1.22l.104-.01.26-.022.104-.008C2.88 1.9 3.03 1.9 8.05 1.999z"/>
            </svg>
          </a>
        </div>
      </div>
    </div>

    <!-- Copyright Bar -->
    <div class="copyright-bar">
      <div class="container copyright-container">
        <p>&copy; {{ currentYear }} Anom Elektronik. Hak Cipta Dilindungi Undang-Undang.</p>
        <div class="footer-bottom-links">
          <a href="#">Syarat & Ketentuan</a>
          <span class="dot-sep">•</span>
          <a href="#">Kebijakan Privasi</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer-wrapper {
  margin-top: 100px;
  background-color: var(--bg-card);
  border-top: 1px solid var(--border);
  padding-top: 80px;
  position: relative;
  z-index: 1;
}

.footer-container {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr 1fr;
  gap: 48px;
  padding-bottom: 60px;
}

.footer-info-col {
  text-align: left;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 10px;
  font-family: var(--font-heading);
  font-weight: 700;
  font-size: 1.25rem;
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

.footer-desc {
  color: var(--text-muted);
  font-size: 0.9rem;
  line-height: 1.6;
}

.footer-links-col {
  text-align: left;
}

.footer-links-col h4 {
  font-size: 1rem;
  font-weight: 700;
  color: var(--text-strong);
  margin-bottom: 24px;
}

.footer-links {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.footer-links a {
  font-size: 0.9rem;
  color: var(--text-muted);
}

.footer-links a:hover {
  color: var(--primary);
  padding-left: 4px;
  transition: all var(--transition-fast);
}

.social-row {
  display: flex;
  gap: 12px;
}

.social-icon-box {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  background-color: var(--bg);
  border: 1px solid var(--border);
  color: var(--text-strong);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all var(--transition-fast);
}

.social-icon-box:hover {
  background-color: var(--primary);
  color: var(--text-white);
  border-color: transparent;
  transform: translateY(-2px);
}

/* Copyright Bar styling */
.copyright-bar {
  border-top: 1px solid var(--border);
  padding: 24px 0;
  background-color: var(--bg);
}

.copyright-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.82rem;
  color: var(--text-muted);
}

.footer-bottom-links {
  display: flex;
  align-items: center;
  gap: 12px;
}

.footer-bottom-links a:hover {
  color: var(--primary);
}

.dot-sep {
  opacity: 0.5;
}

/* Responsive styles */
@media (max-width: 992px) {
  .footer-container {
    grid-template-columns: 1fr 1fr;
    gap: 40px;
  }
}

@media (max-width: 576px) {
  .footer-wrapper {
    padding-top: 60px;
    margin-top: 60px;
  }
  
  .footer-container {
    grid-template-columns: 1fr;
    gap: 32px;
  }
  
  .copyright-container {
    flex-direction: column;
    gap: 12px;
    text-align: center;
  }
}
</style>
