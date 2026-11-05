<template>
  <section class="hero-section" id="home">
    <div class="container">
      <div class="row align-items-center hero-grid">
        <!-- Left: Punchy Headline & Direct Actions -->
        <div class="col-lg-6 hero-text-col">
          <p class="hero-category-text">
            Bengkel Las &amp; Kaca Tempered Medan
          </p>

          <h1 class="hero-title">
            Bikin Kanopi &amp; Pagar Impian, Rapi dan Bergaransi
          </h1>

          <p class="hero-lead">
            Spesialis kanopi kaca tempered, pagar minimalis, pintu sliding, dan partisi shower di Medan. Bisa custom model apa saja sesuai selera &amp; budget. Gratis survey langsung ke rumah Anda.
          </p>

          <div class="hero-actions">
            <a 
              class="button button-primary hero-btn-main" 
              href="https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20pembuatan%20kanopi/pagar" 
              target="_blank" 
              rel="noopener noreferrer"
            >
              <span class="fa-brands fa-whatsapp" style="font-size: 17px;"></span>
              <span>Konsultasi via WA</span>
            </a>
          </div>

          <div class="hero-wa-hint">
            <span class="fa-solid fa-camera text-primary"></span>
            <span>Punya foto model dari Pinterest atau Google? Kirim ke WA, langsung kami hitung biayanya!</span>
          </div>

          <!-- Trust Strip: 3 Clean Value Markers -->
          <div class="hero-trust-strip">
            <div class="trust-item">
              <span class="trust-num">10+ Thn</span>
              <span class="trust-label">Pengalaman Las</span>
            </div>
            <div class="trust-divider"></div>
            <div class="trust-item">
              <span class="trust-num">GRATIS</span>
              <span class="trust-label">Survey ke Rumah</span>
            </div>
            <div class="trust-divider"></div>
            <div class="trust-item">
              <span class="trust-num">100%</span>
              <span class="trust-label">Garansi Sambungan</span>
            </div>
          </div>
        </div>

        <!-- Right: Visual-First Showcase Card with Real Photos -->
        <div class="col-lg-6 hero-visual-col">
          <div class="hero-card-frame">
            <div class="hero-media-wrap">
              <img 
                :src="slides[activeSlide].image" 
                :alt="slides[activeSlide].title" 
                class="hero-media-img"
              />
              <!-- Floating Visual Proof Pills -->
              <div class="hero-floating-badges">
                <span class="badge-pill-frosted">
                  <span class="fa-solid fa-location-dot text-primary"></span>
                  Foto Asli Proyek
                </span>
                <span class="badge-pill-frosted">
                  <span class="fa-solid fa-certificate text-primary"></span>
                  Garansi Rapi
                </span>
              </div>

              <div class="hero-media-caption">
                <div class="hero-caption-title">{{ slides[activeSlide].title }}</div>
                <div class="hero-caption-sub">{{ slides[activeSlide].desc }}</div>
              </div>
            </div>

            <!-- Apple Segmented Control 4 Kategori Proyek (§4, §6) -->
            <div class="hero-segmented-wrap">
              <div class="hero-slide-switchers" role="tablist">
                <button 
                  v-for="(slide, idx) in slides" 
                  :key="idx" 
                  class="hero-switch-btn" 
                  :class="{ 'switch-active': activeSlide === idx }"
                  @click="activeSlide = idx"
                  type="button"
                  role="tab"
                  :aria-selected="activeSlide === idx"
                >
                  {{ slide.tabName }}
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const activeSlide = ref(0)

const slides = [
  {
    tabName: 'Kanopi Kaca',
    title: 'Kanopi Kaca Tempered Carport',
    desc: 'Rangka besi hollow galvanis kokoh dengan atap kaca tempered tebal tahan benturan.',
    image: '/images/chico/atap 1.jpg'
  },
  {
    tabName: 'Pagar Modern',
    title: 'Pagar Besi Minimalis Anti-Karat',
    desc: 'Model kisi-kisi rapi dan cat tahan karat untuk rumah modern di Medan.',
    image: '/images/chico/pagar 1.jpg'
  },
  {
    tabName: 'Pintu Sliding',
    title: 'Pintu Geser Kaca & Aluminium',
    desc: 'Rel geser senyap, hemat tempat, cocok untuk pintu utama, taman, maupun penyekat.',
    image: '/images/chico/pintu 1.webp'
  },
  {
    tabName: 'Partisi Shower',
    title: 'Partisi Kaca Shower Tempered',
    desc: 'Kaca tempered 10mm dengan fitting stainless SUS 304 anti-karat basah.',
    image: '/images/chico/shower 1.jpg'
  }
]
</script>

<style scoped>
.hero-section {
  position: relative;
  background-color: var(--background);
  padding: 84px 0 90px;
  border-bottom: 1px solid var(--border);
  overflow: hidden;
}

@media (max-width: 991px) {
  .hero-section {
    padding: 54px 0 60px;
  }
}

.hero-grid {
  row-gap: 40px;
}

.hero-category-text {
  font-family: var(--font-sans);
  font-size: 11.5px;
  font-weight: 700;
  color: var(--primary);
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin-bottom: 14px;
}

.hero-title {
  color: var(--foreground);
  font-weight: 700;
  font-size: clamp(28px, 3.6vw, 44px);
  line-height: 1.15;
  letter-spacing: -0.035em;
  margin-bottom: 18px;
}

.hero-lead {
  color: var(--muted-foreground);
  font-size: 16px;
  line-height: 1.6;
  letter-spacing: -0.01em;
  margin-bottom: 26px;
  max-width: 530px;
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 12px;
  margin-bottom: 16px;
}

.hero-btn-main {
  white-space: nowrap;
}

.hero-wa-hint {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 13px;
  color: var(--muted-foreground);
  margin-bottom: 32px;
  line-height: 1.45;
}

/* Mobile Typography & Layout Centering */
@media (max-width: 767px) {
  .hero-text-col {
    text-align: center;
  }

  .hero-category-text {
    text-align: center;
  }

  .hero-title {
    text-align: center;
  }

  .hero-lead {
    text-align: center;
    margin-left: auto;
    margin-right: auto;
  }

  .hero-actions {
    justify-content: center;
    margin-bottom: 14px;
  }

  .hero-btn-main {
    width: 100%;
    max-width: 290px;
    margin: 0 auto;
    justify-content: center;
  }

  .hero-wa-hint {
    justify-content: center;
    text-align: center;
    font-size: 12px;
    margin-bottom: 28px;
  }
}

/* Trust Strip: Responsive 3-Column Clean Layout */
.hero-trust-strip {
  display: grid;
  grid-template-columns: 1fr auto 1fr auto 1fr;
  align-items: center;
  gap: 18px;
  padding-top: 24px;
  border-top: 1px solid var(--border);
  text-align: center;
}

@media (max-width: 767px) {
  .hero-trust-strip {
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    padding-top: 20px;
  }

  .trust-divider {
    display: none;
  }
}

.trust-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.trust-num {
  font-family: var(--font-sans);
  font-weight: 700;
  font-size: 19px;
  color: var(--primary);
  line-height: 1.2;
  letter-spacing: -0.02em;
}

.trust-label {
  font-size: 11.5px;
  color: var(--muted-foreground);
  margin-top: 4px;
  line-height: 1.35;
  text-align: center;
}

.trust-divider {
  width: 1px;
  height: 28px;
  background: var(--border);
}

/* Right Apple Visual Frame (§12) */
.hero-card-frame {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-xl);
  overflow: hidden;
  box-shadow: var(--shadow-lg);
  transition: transform 0.3s var(--spring-damp), box-shadow 0.3s var(--spring-damp);
}

.hero-media-wrap {
  position: relative;
  width: 100%;
  height: 380px;
  background: var(--secondary);
  overflow: hidden;
}

@media (min-width: 992px) {
  .hero-media-wrap {
    height: 420px;
  }
}

.hero-media-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: opacity 0.3s var(--spring-damp);
}

.hero-floating-badges {
  position: absolute;
  top: 16px;
  left: 16px;
  right: 16px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  pointer-events: none;
  z-index: 2;
}

.badge-pill-frosted {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 12px;
  background: rgba(255, 255, 255, 0.88);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border-radius: var(--radius-full);
  font-size: 11.5px;
  font-weight: 600;
  color: var(--foreground);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
  border: 1px solid rgba(255, 255, 255, 0.6);
}

.hero-media-caption {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 24px 20px 18px;
  background: linear-gradient(180deg, rgba(0, 0, 0, 0) 0%, rgba(29, 29, 31, 0.9) 100%);
  color: #ffffff;
  text-align: left;
}

.hero-caption-title {
  font-family: var(--font-sans);
  font-weight: 600;
  font-size: 15px;
  letter-spacing: -0.01em;
  margin-bottom: 4px;
  color: #ffffff;
}

.hero-caption-sub {
  font-size: 12px;
  color: #d2d2d7;
  line-height: 1.45;
}

/* Apple Segmented Control (§4, §6) */
.hero-segmented-wrap {
  padding: 8px 12px;
  background: #ffffff;
  border-top: 1px solid var(--border);
}

.hero-slide-switchers {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  background: var(--secondary);
  padding: 3px;
  border-radius: 11px;
  gap: 3px;
}

.hero-switch-btn {
  padding: 9px 4px;
  font-family: var(--font-sans);
  font-size: 11.5px;
  font-weight: 500;
  letter-spacing: -0.01em;
  color: var(--muted-foreground);
  background: transparent;
  border: none;
  border-radius: 9px;
  cursor: pointer;
  text-align: center;
  transition: all 0.2s var(--spring-damp);
  outline: none;
  white-space: nowrap;
}

.hero-switch-btn:hover {
  color: var(--foreground);
}

.hero-switch-btn:active {
  transform: scale(0.96);
  transition: transform 100ms var(--spring-fast);
}

.switch-active {
  color: var(--foreground) !important;
  font-weight: 600 !important;
  background: #ffffff !important;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.08), 0 1px 2px rgba(0, 0, 0, 0.04) !important;
}
</style>
