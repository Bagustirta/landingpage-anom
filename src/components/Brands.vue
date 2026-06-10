<template>
  <section class="brands-section">
    <div class="container">
      <div class="brands-header">
        <h4 class="brands-title">Hanya Menyediakan Merk Terbaik & Resmi</h4>
      </div>
      <div class="brands-grid">
        <div class="brand-item glass">
          <span class="brand-name text-pertamina">PERTAMINA LPG</span>
        </div>
        <div class="brand-item glass">
          <span class="brand-name text-bright">BRIGHT GAS</span>
        </div>
        <div class="brand-item glass">
          <span class="brand-name text-rinnai">RINNAI</span>
        </div>
        <div class="brand-item glass">
          <span class="brand-name text-quantum">QUANTUM</span>
        </div>
        <div class="brand-item glass">
          <span class="brand-name text-maspion">MASPION</span>
        </div>
        <div class="brand-item glass">
          <span class="brand-name text-miyako">MIYAKO</span>
        </div>
        <div class="brand-item glass">
          <span class="brand-name text-cosmos">COSMOS</span>
        </div>
        <div class="brand-item glass">
          <span class="brand-name text-philips">PHILIPS</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.brands-section {
  padding: 40px 0;
  background-color: var(--bg);
  border-bottom: 1px solid var(--border);
}

.brands-header {
  text-align: center;
  margin-bottom: 24px;
}

.brands-title {
  font-size: 0.9rem;
  font-weight: 700;
  color: var(--text-muted);
  text-transform: uppercase;
  letter-spacing: 1.5px;
}

.brands-grid {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  gap: 16px;
  align-items: center;
}

.brand-item {
  padding: 14px;
  border-radius: var(--radius-sm);
  display: flex;
  align-items: center;
  justify-content: center;
  height: 54px;
  transition: all var(--transition-fast);
  cursor: default;
  border: 1px solid var(--border);
}

.brand-item:hover {
  border-color: var(--primary);
  background: var(--bg-card);
  transform: translateY(-2px);
  box-shadow: var(--shadow-sm);
}

.brand-name {
  font-size: 0.9rem;
  font-weight: 800;
  letter-spacing: 0.5px;
  opacity: 0.7;
  transition: opacity var(--transition-fast);
}

.brand-item:hover .brand-name {
  opacity: 1;
}

/* Custom styling for brand colors to make it look colorful! */
.text-pertamina {
  color: #e53e3e; /* Pertamina Red */
}

.text-bright {
  color: #ed64a6; /* Bright Gas Pink */
}

.text-rinnai {
  color: #3182ce; /* Rinnai Blue */
}

.text-quantum {
  color: #dd6b20; /* Quantum Orange */
}

.text-maspion {
  color: #38a169; /* Maspion Green */
}

.text-miyako {
  color: #ecc94b; /* Miyako Yellow/Gold */
}

.text-cosmos {
  color: #805ad5; /* Cosmos Violet */
}

.text-philips {
  color: #319795; /* Philips Teal */
}

/* Responsive Layout */
@media (max-width: 1024px) {
  .brands-grid {
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
  }
}

@media (max-width: 640px) {
  .brands-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
  }
  
  .brand-item {
    height: 48px;
    padding: 10px;
  }
  
  .brand-name {
    font-size: 0.8rem;
  }
}
</style>
