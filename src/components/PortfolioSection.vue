<template>
  <section class="portfolio-section section-lg bg-muted" id="portfolio">
    <div class="container">
      <!-- Section Header with Integrated Navigation Controls -->
      <div class="row align-items-end justify-content-between portfolio-header-row">
        <div class="col-lg-8 text-center text-lg-left">
          <h2 class="portfolio-title">
            Galeri Portofolio Proyek
          </h2>
          <p class="portfolio-desc">
            Dokumentasi pengerjaan nyata kanopi, pagar minimalis, pintu geser, partisi kaca, dan pengelasan presisi Bengkel Las Chico Mandiri di Medan &amp; Deli Serdang.
          </p>
        </div>

        <div class="col-12 col-lg-4 text-center text-lg-right mt-3 mt-lg-0">
          <div class="portfolio-nav-controls">
            <button 
              class="portfolio-nav-btn" 
              @click="prevProject"
              type="button" 
              aria-label="Proyek Sebelumnya"
            >
              <span class="fa-solid fa-arrow-left"></span>
            </button>
            <span class="portfolio-counter">
              {{ currentIndex + 1 }} / {{ projects.length }}
            </span>
            <button 
              class="portfolio-nav-btn" 
              @click="nextProject"
              type="button" 
              aria-label="Proyek Selanjutnya"
            >
              <span class="fa-solid fa-arrow-right"></span>
            </button>
          </div>
        </div>
      </div>

      <!-- Main Showcase Featured Card -->
      <div class="showcase-card">
        <div class="row no-gutters align-items-stretch">
          <!-- Large Image Section (60% on desktop) -->
          <div class="col-lg-7">
            <div class="showcase-media-box">
              <img 
                :src="currentProject.image" 
                :alt="currentProject.title"
                class="showcase-img"
              />
              <div class="showcase-image-tag">
                <span class="fa-solid fa-location-dot text-primary" style="margin-right: 6px;"></span>
                {{ currentProject.location }}
              </div>
            </div>
          </div>

          <!-- Project Details Section (40% on desktop) -->
          <div class="col-lg-5">
            <div class="showcase-info-box">
              <div class="showcase-category">
                {{ currentProject.category }}
              </div>

              <h3 class="showcase-title">
                {{ currentProject.title }}
              </h3>

              <p class="showcase-desc">
                {{ currentProject.description }}
              </p>
              
              <div class="showcase-specs-list">
                <div class="showcase-spec-item" v-for="(spec, sIdx) in currentProject.specs" :key="sIdx">
                  <span class="fa-solid fa-circle-check text-primary" style="margin-right: 8px;"></span>
                  <span>{{ spec }}</span>
                </div>
              </div>

              <div class="showcase-action">
                <a 
                  class="button button-primary showcase-cta-btn" 
                  :href="currentProject.waLink" 
                  target="_blank" 
                  rel="noopener noreferrer"
                >
                  <span class="fa-brands fa-whatsapp"></span>
                  <span>Tanya Model Ini via WA</span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Thumbnails Selector Grid below showcase -->
      <div class="thumbs-grid mt-4">
        <div 
          v-for="(proj, idx) in projects" 
          :key="proj.id"
          class="thumb-card"
          :class="{ 'thumb-active': currentIndex === idx }"
          @click="currentIndex = idx"
        >
          <img :src="proj.image" :alt="proj.title" class="thumb-photo" />
          <div class="thumb-label">{{ proj.shortName }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const currentIndex = ref(0)

const projects = [
  {
    id: 1,
    shortName: 'Pagar Minimalis',
    category: 'Metal Works &bull; Medan',
    location: 'Proyek Selesai di Medan',
    title: 'Pagar Minimalis Besi Hollow Galvanis Modern',
    description: 'Pengerjaan pagar minimalis bahan besi hollow galvanis tebal anti-karat dengan finishing cat hitam matte tahan cuaca ekstrem. Konstruksi kokoh dan hasil pengelasan rapi presisi.',
    specs: [
      'Besi hollow galvanis tebal anti-karat',
      'Cat epoxy tahan panas dan hujan',
      'Kunci pengaman & bearing roda halus'
    ],
    image: '/images/chico/pagar 2.jpg',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20dengan%20proyek%20Pagar%20Minimalis%20di%20galeri'
  },
  {
    id: 2,
    shortName: 'Kanopi Kaca Tempered',
    category: 'Kanopi &bull; Deli Serdang',
    location: 'Proyek Selesai di Deli Serdang',
    title: 'Kanopi Kaca Tempered & Rangka Struktur Besi',
    description: 'Struktur rangka kanopi besi galvanis kokoh dipadu atap kaca tempered berstandar keamanan SNI. Memberikan perlindungan maksimal dari panas dan hujan sekaligus menambah kemewahan fasad rumah.',
    specs: [
      'Kaca tempered SNI tahan benturan',
      'Rangka besi hollow presisi tinggi',
      'Talang air & sealant anti-bocor'
    ],
    image: '/images/chico/proyek-kanopi-modern.jpg',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20dengan%20proyek%20Kanopi%20Kaca%20di%20galeri'
  },
  {
    id: 3,
    shortName: 'Partisi Kaca Shower',
    category: 'Glass (Kaca) &bull; Medan',
    location: 'Proyek Interior Selesai di Medan',
    title: 'Partisi Kaca Shower Tempered Mewah',
    description: 'Pemasangan sekat kaca kamar mandi tempered presisi dengan engsel, pegangan, dan fitting stainless steel SUS 304 anti-karat. Menghadirkan suasana kamar mandi yang bersih, elegan, dan eksklusif.',
    specs: [
      'Kaca tempered 10mm standar SNI',
      'Hardware stainless 304 anti-karat basah',
      'Seal karet kedap air presisi'
    ],
    image: '/images/chico/shower 2.webp',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20dengan%20proyek%20Partisi%20Kaca%20Shower%20di%20galeri'
  },
  {
    id: 4,
    shortName: 'Pagar Laser Cutting',
    category: 'Laser Cutting Art &bull; Medan',
    location: 'Proyek Selesai di Medan',
    title: 'Pagar Plat Besi Motif Laser Cutting Artistik',
    description: 'Pagar hunian eksklusif dengan motif laser cutting komputer presisi tinggi. Desain ornamen modern yang memberikan privasi optimal serta tampilan arsitektur fasad mewah.',
    specs: [
      'Plat besi cutting CNC presisi tinggi',
      'Motif kustom sesuai selera pelanggan',
      'Cat oven tahan gores & anti-karat'
    ],
    image: '/images/chico/pagar 3.webp',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20dengan%20proyek%20Pagar%20Laser%20Cutting%20di%20galeri'
  },
  {
    id: 5,
    shortName: 'Workshop Fabrikasi',
    category: 'Workshop Chico Mandiri &bull; Medan',
    location: 'Workshop Jl. Roso No. 8, Medan',
    title: 'Fabrikasi Bengkel Las & Quality Control Presisi',
    description: 'Setiap pesanan dirakit dan difabrikasi di workshop kami di Jl. Roso No. 8, Deli Tua – Marendal. Seluruh titik sambungan las diuji kekuatannya sebelum pemasangan ke lokasi Anda.',
    specs: [
      'Pengelasan presisi standar konstruksi',
      'Pemeriksaan mutu sebelum pemasangan',
      'Garansi resmi kekuatan struktur'
    ],
    image: '/images/chico/workshop-las.jpg',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20ingin%20konsultasi%20langsung%20ke%20workshop'
  }
]

const currentProject = computed(() => projects[currentIndex.value] || projects[0])

function nextProject() {
  currentIndex.value = (currentIndex.value + 1) % projects.length
}

function prevProject() {
  currentIndex.value = (currentIndex.value - 1 + projects.length) % projects.length
}
</script>

<style scoped>
.portfolio-section {
  position: relative;
  background-color: var(--muted);
  border-bottom: 1px solid var(--border);
}

.portfolio-header-row {
  margin-bottom: 28px;
}

.portfolio-title {
  font-weight: 800;
  font-size: clamp(24px, 2.8vw, 32px);
  color: var(--foreground);
  margin-bottom: 8px;
}

.portfolio-desc {
  color: var(--muted-foreground);
  font-size: 15px;
  max-width: 600px;
  line-height: 1.6;
  margin: 0;
}

/* Navigation Controls */
.portfolio-nav-controls {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

.portfolio-nav-btn {
  width: 40px;
  height: 40px;
  border-radius: var(--radius);
  background: var(--card);
  border: 1px solid var(--border);
  color: var(--foreground);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-size: 13px;
  cursor: pointer;
  transition: all 0.15s ease;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.04);
}

.portfolio-nav-btn:hover {
  background: var(--secondary);
  border-color: #cbd5e1;
  color: var(--primary);
}

.portfolio-counter {
  font-family: var(--font-sans), sans-serif;
  font-weight: 600;
  font-size: 13.5px;
  color: var(--muted-foreground);
  min-width: 48px;
  text-align: center;
}

/* Main Showcase Card */
.showcase-card {
  background: var(--card);
  border-radius: 12px;
  overflow: hidden;
  border: 1px solid var(--border);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
}

.showcase-media-box {
  position: relative;
  width: 100%;
  height: 330px;
  background: var(--secondary);
  overflow: hidden;
}

@media (min-width: 992px) {
  .showcase-media-box {
    height: 100%;
    min-height: 460px;
  }
}

.showcase-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.showcase-image-tag {
  position: absolute;
  bottom: 14px;
  left: 14px;
  padding: 6px 12px;
  background: rgba(255, 255, 255, 0.95);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  color: var(--foreground);
  font-size: 12px;
  font-weight: 600;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.08);
}

.showcase-info-box {
  padding: 32px 28px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
  background: var(--card);
  color: var(--foreground);
}

@media (min-width: 992px) {
  .showcase-info-box {
    padding: 38px 34px;
  }
}

.showcase-category {
  font-family: var(--font-sans), sans-serif;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.5px;
  color: var(--primary);
  text-transform: uppercase;
  margin-bottom: 8px;
}

.showcase-title {
  font-family: var(--font-sans), sans-serif;
  font-weight: 800;
  font-size: clamp(20px, 2.2vw, 25px);
  line-height: 1.3;
  color: var(--foreground);
  margin-bottom: 12px;
}

.showcase-desc {
  font-size: 14px;
  line-height: 1.6;
  color: var(--muted-foreground);
  margin-bottom: 20px;
}

.showcase-specs-list {
  margin-bottom: 24px;
  display: flex;
  flex-direction: column;
  gap: 9px;
}

.showcase-spec-item {
  font-size: 13px;
  color: var(--foreground);
  display: flex;
  align-items: center;
}

.showcase-action {
  margin-top: auto;
}

.showcase-cta-btn {
  width: 100%;
  white-space: nowrap;
}

@media (max-width: 767px) {
  .portfolio-header-row {
    text-align: center;
  }

  .portfolio-desc {
    margin-left: auto;
    margin-right: auto;
  }

  .showcase-info-box {
    text-align: center;
    padding: 26px 18px;
  }

  .showcase-specs-list {
    text-align: left;
    max-width: 340px;
    margin-left: auto;
    margin-right: auto;
  }

  .showcase-cta-btn {
    max-width: 280px;
    margin: 0 auto;
  }
}

/* Thumbnails Grid */
.thumbs-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
}

@media (min-width: 576px) {
  .thumbs-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (min-width: 992px) {
  .thumbs-grid {
    grid-template-columns: repeat(5, 1fr);
    gap: 12px;
  }
}

.thumb-card {
  position: relative;
  height: 90px;
  border-radius: var(--radius);
  overflow: hidden;
  cursor: pointer;
  border: 1px solid var(--border);
  transition: all 0.15s ease;
  background: var(--card);
}

.thumb-card:hover {
  border-color: #94a3b8;
}

.thumb-active {
  border-color: var(--primary) !important;
  box-shadow: 0 0 0 2px var(--ring) !important;
}

.thumb-photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.thumb-label {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 4px 6px;
  background: rgba(255, 255, 255, 0.94);
  color: var(--foreground);
  font-size: 11px;
  font-weight: 600;
  text-align: center;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  border-top: 1px solid var(--border);
}
</style>
