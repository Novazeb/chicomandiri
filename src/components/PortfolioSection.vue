<template>
  <section class="portfolio-section section-lg bg-muted" id="portfolio">
    <div class="container">
      <!-- Section Header -->
      <div class="section-heading text-center">
        <h2 class="portfolio-title">
          Galeri Foto Proyek Asli
        </h2>
        <p class="portfolio-desc">
          Dokumentasi pengerjaan nyata kanopi, pagar minimalis, pintu geser, dan partisi kaca Bengkel Las Chico Mandiri di wilayah Medan &amp; Deli Serdang.
        </p>
      </div>

      <!-- Category Filter Pills (Apple Segmented Style §4, §6) -->
      <div class="portfolio-filters-wrap">
        <div class="portfolio-filter-nav" role="tablist">
          <button 
            v-for="cat in categories" 
            :key="cat.key" 
            class="filter-pill-btn" 
            :class="{ 'filter-active': activeCategory === cat.key }"
            @click="activeCategory = cat.key"
            type="button"
          >
            {{ cat.label }} ({{ getCategoryCount(cat.key) }})
          </button>
        </div>
      </div>

      <!-- Responsive Photo Gallery Grid -->
      <div class="row row-20 gallery-grid">
        <div 
          v-for="item in filteredProjects" 
          :key="item.id" 
          class="col-12 col-sm-6 col-lg-4 gallery-col"
        >
          <div class="gallery-card">
            <!-- Photo Box with Click to Enlarge -->
            <div class="gallery-photo-box" @click="openModal(item)">
              <img :src="item.image" :alt="item.title" class="gallery-img" />
              <div class="gallery-location-pill">
                <span class="fa-solid fa-location-dot text-primary"></span>
                <span>{{ item.location }}</span>
              </div>
              <div class="gallery-overlay-hint">
                <span class="fa-solid fa-expand"></span>
                <span>Lihat Foto Penuh</span>
              </div>
            </div>

            <!-- Card Bottom Bar: Title & Direct WhatsApp Action -->
            <div class="gallery-card-body">
              <span class="gallery-cat-tag">{{ item.category }}</span>
              <h4 class="gallery-card-title">{{ item.title }}</h4>

              <div class="gallery-card-footer">
                <a 
                  class="button button-primary gallery-wa-btn" 
                  :href="getWaLink(item)" 
                  target="_blank" 
                  rel="noopener noreferrer"
                >
                  <span class="fa-brands fa-whatsapp"></span>
                  <span>Konsultasi via WA</span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Visual Bottom Banner: Kirim Foto dari Pinterest/IG -->
      <div class="portfolio-custom-banner">
        <div class="row align-items-center justify-content-between">
          <div class="col-lg-8 text-center text-lg-left mb-3 mb-lg-0">
            <div class="custom-banner-icon d-none d-lg-flex">
              <span class="fa-brands fa-pinterest text-primary"></span>
            </div>
            <div class="custom-banner-text">
              <h4 class="custom-banner-title">Punya Contoh Model dari Pinterest atau Google?</h4>
              <p class="custom-banner-desc">Kirim foto desain yang Anda sukai ke WhatsApp kami. Tim kami siap survey ke rumah dan hitung estimasi biayanya gratis!</p>
            </div>
          </div>
          <div class="col-lg-4 text-center text-lg-right">
            <a 
              class="button button-primary custom-banner-btn" 
              href="https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20punya%20foto%20contoh%20model%20yang%20mau%20dikonsultasikan" 
              target="_blank" 
              rel="noopener noreferrer"
            >
              <span class="fa-brands fa-whatsapp"></span>
              <span>Konsultasi via WA</span>
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Image Lightbox Modal Preview -->
    <div v-if="selectedProject" class="modal-backdrop" @click="closeModal">
      <div class="modal-dialog-box" @click.stop>
        <button class="modal-close-btn" @click="closeModal" aria-label="Tutup">
          <span class="fa-solid fa-xmark"></span>
        </button>
        <img :src="selectedProject.image" :alt="selectedProject.title" class="modal-preview-img" />
        <div class="modal-info-bar">
          <div>
            <div class="modal-project-title">{{ selectedProject.title }}</div>
            <div class="modal-project-loc">
              <span class="fa-solid fa-location-dot text-primary"></span>
              {{ selectedProject.location }} &bull; {{ selectedProject.category }}
            </div>
          </div>
          <a 
            class="button button-primary modal-wa-btn" 
            :href="getWaLink(selectedProject)" 
            target="_blank" 
            rel="noopener noreferrer"
          >
            <span class="fa-brands fa-whatsapp"></span>
            <span>Konsultasi via WA</span>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const activeCategory = ref('all')
const selectedProject = ref(null)

const categories = [
  { key: 'all', label: 'Semua Foto' },
  { key: 'kanopi', label: 'Kanopi' },
  { key: 'pagar', label: 'Pagar & Gerbang' },
  { key: 'kaca', label: 'Pintu & Partisi Kaca' }
]

const projects = [
  {
    id: 1,
    catKey: 'kanopi',
    category: 'Kanopi Kaca',
    title: 'Kanopi Kaca Tempered Carport',
    location: 'Medan Johor',
    image: '/images/chico/atap 1.jpg'
  },
  {
    id: 2,
    catKey: 'kanopi',
    category: 'Kanopi Modern',
    title: 'Kanopi Rangka Gantung Minimalis',
    location: 'Deli Tua – Marendal',
    image: '/images/chico/proyek-kanopi-modern.jpg'
  },
  {
    id: 3,
    catKey: 'pagar',
    category: 'Pagar Minimalis',
    title: 'Pagar Besi Hollow Hitam Doff',
    location: 'Komplek Tasbi, Medan',
    image: '/images/chico/pagar 1.jpg'
  },
  {
    id: 4,
    catKey: 'pagar',
    category: 'Pagar Kombinasi',
    title: 'Pagar Hollow Galvanis & Plat',
    location: 'Ringroad, Medan',
    image: '/images/chico/pagar 2.jpg'
  },
  {
    id: 5,
    catKey: 'pagar',
    category: 'Pagar Gerbang',
    title: 'Pagar Gerbang Dorong Minimalis',
    location: 'Setia Budi, Medan',
    image: '/images/chico/pagar 3.webp'
  },
  {
    id: 6,
    catKey: 'kaca',
    category: 'Pintu Aluminium',
    title: 'Pintu Sliding Kaca & Aluminium',
    location: 'Cemara Asri, Medan',
    image: '/images/chico/pintu 1.webp'
  },
  {
    id: 7,
    catKey: 'kaca',
    category: 'Partisi Kaca',
    title: 'Partisi Shower Box Kaca Tempered',
    location: 'Krakatau, Medan',
    image: '/images/chico/shower 1.jpg'
  },
  {
    id: 8,
    catKey: 'kaca',
    category: 'Shower Screen',
    title: 'Partisi Kamar Mandi Frameless 10mm',
    location: 'Helvetia, Medan',
    image: '/images/chico/shower 2.webp'
  }
]

const filteredProjects = computed(() => {
  if (activeCategory.value === 'all') return projects
  return projects.filter(p => p.catKey === activeCategory.value)
})

function getCategoryCount(key) {
  if (key === 'all') return projects.length
  return projects.filter(p => p.catKey === key).length
}

function getWaLink(item) {
  const text = `Halo Bengkel Las Chico Mandiri, saya tertarik dengan model foto ini: ${item.title} (${item.location}). Berapa perkiraan biaya pengerjaannya?`
  return `https://wa.me/6281376933039?text=${encodeURIComponent(text)}`
}

function openModal(item) {
  selectedProject.value = item
}

function closeModal() {
  selectedProject.value = null
}
</script>

<style scoped>
.portfolio-section {
  position: relative;
  background-color: var(--muted);
  border-bottom: 1px solid var(--border);
}

.section-heading {
  margin-bottom: 34px;
}

.portfolio-title {
  color: var(--foreground);
  font-weight: 700;
  font-size: clamp(24px, 3vw, 34px);
  letter-spacing: -0.03em;
  margin-bottom: 8px;
}

.portfolio-desc {
  color: var(--muted-foreground);
  font-size: 15.5px;
  max-width: 580px;
  line-height: 1.55;
  letter-spacing: -0.01em;
  margin: 0 auto;
}

/* Category Filter Pills (Apple Segmented Style) */
.portfolio-filters-wrap {
  display: flex;
  justify-content: center;
  margin-bottom: 34px;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  padding: 4px;
}

.portfolio-filter-nav {
  display: inline-flex;
  gap: 6px;
  background: var(--secondary);
  padding: 4px;
  border-radius: var(--radius-full);
  border: 1px solid var(--border);
}

.filter-pill-btn {
  padding: 8px 16px;
  border-radius: var(--radius-full);
  border: none;
  background: transparent;
  color: var(--muted-foreground);
  font-family: var(--font-sans);
  font-size: 12.5px;
  font-weight: 500;
  letter-spacing: -0.01em;
  cursor: pointer;
  transition: all 0.2s var(--spring-damp);
  outline: none;
  white-space: nowrap;
}

.filter-pill-btn:hover {
  color: var(--foreground);
}

.filter-pill-btn:active {
  transform: scale(0.96);
  transition: transform 100ms var(--spring-fast);
}

.filter-active {
  background: #ffffff !important;
  color: var(--foreground) !important;
  font-weight: 600 !important;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.08), 0 1px 2px rgba(0, 0, 0, 0.04) !important;
}

/* Photo Gallery Grid */
.gallery-grid {
  row-gap: 24px;
}

.gallery-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-xl);
  overflow: hidden;
  height: 100%;
  display: flex;
  flex-direction: column;
  box-shadow: var(--shadow-sm);
  transition: transform 0.25s var(--spring-damp), box-shadow 0.25s var(--spring-damp);
}

.gallery-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-md);
}

.gallery-photo-box {
  position: relative;
  width: 100%;
  height: 230px;
  background: var(--secondary);
  overflow: hidden;
  cursor: pointer;
}

@media (min-width: 992px) {
  .gallery-photo-box {
    height: 250px;
  }
}

.gallery-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.6s var(--spring-damp);
}

.gallery-photo-box:hover .gallery-img {
  transform: scale(1.05);
}

.gallery-location-pill {
  position: absolute;
  top: 12px;
  left: 12px;
  display: inline-flex;
  align-items: center;
  gap: 5px;
  padding: 5px 11px;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  border-radius: var(--radius-full);
  font-size: 11px;
  font-weight: 600;
  color: var(--foreground);
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.12);
}

.gallery-overlay-hint {
  position: absolute;
  bottom: 12px;
  right: 12px;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 4px 10px;
  background: rgba(29, 29, 31, 0.78);
  backdrop-filter: blur(6px);
  -webkit-backdrop-filter: blur(6px);
  border-radius: var(--radius-full);
  font-size: 11px;
  color: #ffffff;
  opacity: 0;
  transition: opacity 0.2s ease;
}

.gallery-photo-box:hover .gallery-overlay-hint {
  opacity: 1;
}

.gallery-card-body {
  padding: 20px 18px 22px;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.gallery-cat-tag {
  font-size: 11px;
  font-weight: 600;
  color: var(--primary);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 4px;
}

.gallery-card-title {
  font-family: var(--font-sans);
  font-size: 16px;
  font-weight: 700;
  letter-spacing: -0.015em;
  color: var(--foreground);
  line-height: 1.3;
  margin-bottom: 16px;
}

.gallery-card-footer {
  margin-top: auto;
}

.gallery-wa-btn {
  width: 100%;
  justify-content: center;
  font-size: 13px !important;
  padding: 9px 16px !important;
}

/* Custom Banner below gallery */
.portfolio-custom-banner {
  margin-top: 48px;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 28px 32px;
  box-shadow: var(--shadow-sm);
  transition: box-shadow 0.25s var(--spring-damp);
}

.portfolio-custom-banner:hover {
  box-shadow: var(--shadow-md);
}

.custom-banner-icon {
  width: 48px;
  height: 48px;
  border-radius: 12px;
  background: rgba(0, 113, 227, 0.08);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
  margin-right: 18px;
  flex-shrink: 0;
}

.custom-banner-text {
  display: inline-block;
  vertical-align: middle;
}

.custom-banner-title {
  color: var(--foreground);
  font-size: 18px;
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 4px;
}

.custom-banner-desc {
  color: var(--muted-foreground);
  font-size: 14px;
  letter-spacing: -0.01em;
  margin: 0;
}

.custom-banner-btn {
  white-space: nowrap;
}

@media (max-width: 767px) {
  .portfolio-custom-banner {
    padding: 24px 20px;
    text-align: center;
  }

  .custom-banner-btn {
    width: 100%;
    max-width: 280px;
    margin: 14px auto 0;
  }
}

/* Lightbox Modal */
.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.85);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  z-index: 2000;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
}

.modal-dialog-box {
  position: relative;
  background: var(--card);
  border-radius: var(--radius-xl);
  overflow: hidden;
  max-width: 720px;
  width: 100%;
  box-shadow: var(--shadow-lg);
  display: flex;
  flex-direction: column;
}

.modal-close-btn {
  position: absolute;
  top: 14px;
  right: 14px;
  width: 36px;
  height: 36px;
  border-radius: 50%;
  background: rgba(0, 0, 0, 0.6);
  border: none;
  color: #ffffff;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  z-index: 3;
  font-size: 16px;
  transition: transform 0.15s ease;
}

.modal-close-btn:hover {
  transform: scale(1.08);
}

.modal-preview-img {
  width: 100%;
  max-height: 500px;
  object-fit: contain;
  background: #000000;
}

.modal-info-bar {
  padding: 20px 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  background: var(--card);
  border-top: 1px solid var(--border);
}

.modal-project-title {
  font-family: var(--font-sans);
  font-weight: 700;
  font-size: 16px;
  color: var(--foreground);
}

.modal-project-loc {
  font-size: 12.5px;
  color: var(--muted-foreground);
  margin-top: 2px;
}

.modal-wa-btn {
  white-space: nowrap;
}

@media (max-width: 575px) {
  .modal-info-bar {
    flex-direction: column;
    text-align: center;
    gap: 12px;
  }

  .modal-wa-btn {
    width: 100%;
  }
}
</style>