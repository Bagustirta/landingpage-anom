<script setup>
import { ref } from 'vue';
import { MagnifyingGlassIcon, CheckCircleIcon, ExclamationTriangleIcon, MapPinIcon, ClockIcon } from '@heroicons/vue/24/outline';

const search = ref('');
const isSearching = ref(false);
const penjualan = ref(null);
const klaimGaransis = ref([]);
const errorMessage = ref('');

const searchInvoice = async () => {
    if (!search.value) return;
    
    isSearching.value = true;
    errorMessage.value = '';
    penjualan.value = null;
    klaimGaransis.value = [];
    
    try {
        const response = await fetch(`https://pos.anomelektronik.my.id/api/cek-garansi?no_nota=${search.value}`);
        const data = await response.json();
        
        if (data.success) {
            penjualan.value = data.data.penjualan;
            klaimGaransis.value = data.data.klaim_garansis;
        } else {
            errorMessage.value = data.message || 'Data tidak ditemukan.';
        }
    } catch (error) {
        console.error('Error fetching data:', error);
        errorMessage.value = 'Terjadi kesalahan saat mengambil data dari server.';
    } finally {
        isSearching.value = false;
    }
};

const getStatusColor = (status) => {
    switch (status) {
        case 'Menunggu': return 'status-menunggu';
        case 'Sedang Diservis': return 'status-sedang-diservis';
        case 'Selesai': return 'status-selesai';
        case 'Ditolak': return 'status-ditolak';
        case 'Sudah Diambil': return 'status-sudah-diambil';
        default: return 'status-sudah-diambil';
    }
};

const getStatusIcon = (status) => {
    switch (status) {
        case 'Menunggu': return ClockIcon;
        case 'Sedang Diservis': return MapPinIcon;
        case 'Selesai': return CheckCircleIcon;
        case 'Ditolak': return ExclamationTriangleIcon;
        case 'Sudah Diambil': return CheckCircleIcon;
        default: return CheckCircleIcon;
    }
};

const formatDate = (dateString) => {
    if (!dateString) return '';
    const date = new Date(dateString);
    return date.toLocaleDateString('id-ID', {
        day: '2-digit',
        month: 'long',
        year: 'numeric'
    });
};
</script>

<template>
    <div class="warranty-page">
        <!-- Konten Utama -->
        <main class="warranty-container">
            
            <div class="warranty-header animate-fade-in-up">
                <h2>Lacak Status Garansi</h2>
                <p>Masukkan nomor nota pembelian Anda untuk mengecek progres klaim garansi atau servis secara real-time.</p>
            </div>

            <!-- Search Box -->
            <div class="search-box animate-fade-in-up" style="animation-delay: 0.1s">
                <div class="search-icon">
                    <MagnifyingGlassIcon class="icon" />
                </div>
                <input 
                    v-model="search" 
                    @keyup.enter="searchInvoice" 
                    type="text" 
                    placeholder="Contoh: INV-20260901-001" 
                    class="search-input"
                    :disabled="isSearching"
                />
                <button 
                    @click="searchInvoice" 
                    class="btn-search"
                    :disabled="!search || isSearching"
                >
                    {{ isSearching ? 'Mencari...' : 'Lacak' }}
                </button>
            </div>

            <!-- Error State -->
            <div v-if="errorMessage" class="alert-error animate-fade-in-up">
                <ExclamationTriangleIcon class="icon" />
                <div class="alert-content">
                    <h3>Oops, Ada Masalah</h3>
                    <p>{{ errorMessage }}</p>
                </div>
            </div>

            <!-- Hasil Pencarian -->
            <div v-if="penjualan" class="results-section animate-fade-in-up">
                
                <div class="results-header">
                    <h3>Hasil Pencarian</h3>
                    <span class="invoice-badge">Nota: <strong>{{ penjualan.no_nota }}</strong></span>
                </div>

                <div v-if="klaimGaransis && klaimGaransis.length > 0" class="cards-wrapper">
                    <!-- Kartu Tiket Garansi -->
                    <div v-for="klaim in klaimGaransis" :key="klaim.id" class="warranty-card">
                        <div class="card-main">
                            <div class="card-info">
                                <div class="card-meta">
                                    <span class="klaim-id">ID Klaim: #{{ klaim.id }}</span>
                                    <span class="klaim-date">{{ formatDate(klaim.tanggal_klaim) }}</span>
                                </div>
                                <h4 class="product-name">{{ klaim.produk_nama }}</h4>
                                <div class="complaint-box">
                                    <strong>Keluhan:</strong> "{{ klaim.keluhan }}"
                                </div>
                            </div>
                            
                            <div class="card-status">
                                <div :class="['status-badge', getStatusColor(klaim.status)]">
                                    <component :is="getStatusIcon(klaim.status)" class="icon-sm" />
                                    {{ klaim.status.toUpperCase() }}
                                </div>
                            </div>
                        </div>
                        
                        <div v-if="klaim.solusi" class="card-solution">
                            <h5>
                                <CheckCircleIcon class="icon-xs" /> Solusi / Catatan Toko
                            </h5>
                            <p>{{ klaim.solusi }}</p>
                        </div>
                    </div>
                </div>

                <!-- Empty State -->
                <div v-else class="empty-state">
                    <div class="empty-icon">
                        <CheckCircleIcon class="icon-lg" />
                    </div>
                    <h4>Belum Ada Riwayat Klaim</h4>
                    <p>Nota ditemukan, namun belum ada catatan klaim garansi atau servis untuk transaksi ini.</p>
                </div>
            </div>
        </main>
    </div>
</template>

<style scoped>
.warranty-page {
    min-height: 100vh;
    background-color: var(--bg-alt);
    padding-top: 100px;
    padding-bottom: 60px;
    font-family: var(--font-body);
}

.warranty-container {
    max-width: 800px;
    margin: 0 auto;
    padding: 0 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.warranty-header {
    text-align: center;
    margin-bottom: 40px;
    width: 100%;
}

.warranty-header h2 {
    font-size: 2.5rem;
    color: var(--text-strong);
    margin-bottom: 12px;
}

.warranty-header p {
    color: var(--text-muted);
    font-size: 1.1rem;
    max-width: 600px;
    margin: 0 auto;
}

.search-box {
    width: 100%;
    background-color: var(--bg-card);
    padding: 8px;
    border-radius: var(--radius-lg);
    box-shadow: var(--shadow-md);
    border: 1px solid var(--border);
    display: flex;
    align-items: center;
    margin-bottom: 40px;
    transition: all var(--transition-normal);
}

.search-box:focus-within {
    border-color: var(--primary);
    box-shadow: 0 0 0 4px var(--border-glow);
}

.search-icon {
    padding: 0 16px;
    color: var(--text-muted);
}

.icon {
    width: 24px;
    height: 24px;
}

.search-input {
    flex-grow: 1;
    background: transparent !important;
    border: none !important;
    outline: none !important;
    font-size: 1.1rem;
    font-weight: 600;
    color: var(--text-strong);
    padding: 12px 8px;
}

.search-input::placeholder {
    color: #cbd5e1;
    font-weight: 400;
}

.btn-search {
    background-color: var(--primary) !important;
    color: white !important;
    font-weight: 700;
    padding: 14px 32px;
    border-radius: var(--radius-md);
    transition: all var(--transition-fast);
}

.btn-search:hover:not(:disabled) {
    background-color: var(--primary-dark) !important;
    transform: translateY(-2px);
}

.btn-search:disabled {
    opacity: 0.7;
    cursor: not-allowed;
}

.alert-error {
    width: 100%;
    background-color: #fef2f2;
    border: 1px solid #fee2e2;
    padding: 16px;
    border-radius: var(--radius-md);
    display: flex;
    gap: 12px;
    margin-bottom: 30px;
    color: #991b1b;
}

.alert-error .icon {
    color: #ef4444;
    margin-top: 2px;
}

.alert-error h3 {
    color: #991b1b;
    font-size: 1.1rem;
    margin-bottom: 4px;
}

.alert-error p {
    font-size: 0.95rem;
}

.results-section {
    width: 100%;
}

.results-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    padding: 0 8px;
}

.results-header h3 {
    font-size: 1.25rem;
}

.invoice-badge {
    font-size: 0.9rem;
    color: var(--text-muted);
    background: white;
    padding: 6px 12px;
    border-radius: var(--radius-full);
    border: 1px solid var(--border);
}

.invoice-badge strong {
    color: var(--text-strong);
}

.cards-wrapper {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.warranty-card {
    background-color: var(--bg-card);
    border-radius: var(--radius-lg);
    border: 1px solid var(--border);
    box-shadow: var(--shadow-sm);
    overflow: hidden;
    transition: box-shadow var(--transition-normal);
}

.warranty-card:hover {
    box-shadow: var(--shadow-md);
}

.card-main {
    padding: 24px;
    display: flex;
    flex-direction: column;
    gap: 16px;
    border-bottom: 1px solid var(--border);
}

@media (min-width: 768px) {
    .card-main {
        flex-direction: row;
        justify-content: space-between;
    }
}

.card-info {
    flex: 1;
}

.card-meta {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 8px;
}

.klaim-id {
    font-size: 0.75rem;
    font-weight: 700;
    background-color: var(--bg-alt);
    color: var(--text);
    padding: 4px 8px;
    border-radius: 6px;
}

.klaim-date {
    font-size: 0.8rem;
    color: var(--text-muted);
    font-weight: 500;
}

.product-name {
    font-size: 1.3rem;
    margin-bottom: 12px;
}

.complaint-box {
    font-size: 0.9rem;
    color: var(--text);
    background-color: var(--bg-alt);
    padding: 12px;
    border-radius: var(--radius-sm);
    border: 1px solid var(--border);
}

.status-badge {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    border-radius: var(--radius-md);
    font-weight: 700;
    font-size: 0.9rem;
    border: 1px solid transparent;
}

.status-menunggu { background-color: #fef9c3; color: #854d0e; border-color: #fef08a; }
.status-sedang-diservis { background-color: #dbeafe; color: #1e40af; border-color: #bfdbfe; }
.status-selesai { background-color: #dcfce3; color: #166534; border-color: #bbf7d0; }
.status-ditolak { background-color: #fee2e2; color: #991b1b; border-color: #fecaca; }
.status-sudah-diambil { background-color: #f1f5f9; color: #334155; border-color: #e2e8f0; }

.icon-sm { width: 20px; height: 20px; }
.icon-xs { width: 16px; height: 16px; }
.icon-lg { width: 32px; height: 32px; }

.card-solution {
    padding: 20px 24px;
    background-color: #f0f9ff;
}

.card-solution h5 {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 0.8rem;
    color: #0369a1;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: 8px;
}

.card-solution p {
    font-size: 0.95rem;
    color: #0c4a6e;
    font-weight: 500;
}

.empty-state {
    background-color: var(--bg-card);
    border-radius: var(--radius-lg);
    border: 1px solid var(--border);
    padding: 40px 20px;
    text-align: center;
    box-shadow: var(--shadow-sm);
}

.empty-icon {
    width: 64px;
    height: 64px;
    background-color: var(--bg-alt);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 20px;
    color: #94a3b8;
}

.empty-state h4 {
    font-size: 1.2rem;
    margin-bottom: 8px;
}

.empty-state p {
    color: var(--text-muted);
    font-size: 0.95rem;
    max-width: 350px;
    margin: 0 auto;
}

@keyframes fadeInUp {
    from { opacity: 0; transform: translateY(15px); }
    to { opacity: 1; transform: translateY(0); }
}

.animate-fade-in-up {
    animation: fadeInUp 0.5s ease-out forwards;
    opacity: 0;
}
</style>
