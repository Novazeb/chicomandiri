<template>
  <section class="hero-section" id="home">
    <div class="container">
      <div class="row align-items-center hero-grid">
        <!-- Left: Headline & Modern Actions -->
        <div class="col-lg-6 hero-text-col">
          <p class="hero-category-text">
            Metal Works &bull; Alumunium &bull; Glass &bull; Laser Cutting
          </p>

          <h1 class="hero-title">
            Konstruksi Besi Kokoh &amp; Kaca Tempered Presisi di Medan
          </h1>

          <p class="hero-lead">
            Spesialis kanopi kaca tempered, pagar minimalis modern, pintu sliding presisi, dan partisi shower tempered bergaransi resmi. Pengerjaan rapi, besi hollow galvanis anti-karat, dan gratis survey ke lokasi.
          </p>

          <div class="hero-actions">
            <a 
              class="button button-primary hero-btn-main" 
              href="https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20pembuatan%20kanopi/pagar" 
              target="_blank" 
              rel="noopener noreferrer"
            >
              <span class="fa-brands fa-whatsapp" style="font-size: 16px;"></span>
              <span>Konsultasi WhatsApp</span>
            </a>
            <a class="button button-primary-outline hero-btn-sub" href="#portfolio">
              <span>Lihat Portofolio</span>
            </a>
          </div>

          <!-- Trust Strip: 3 Clean Value Markers -->
          <div class="hero-trust-strip">
            <div class="trust-item">
              <span class="trust-num">10+</span>
              <span class="trust-label">Tahun Pengalaman</span>
            </div>
            <div class="trust-divider"></div>
            <div class="trust-item">
              <span class="trust-num">GRATIS</span>
              <span class="trust-label">Survey Medan &amp; Sekitarnya</span>
            </div>
            <div class="trust-divider"></div>
            <div class="trust-item">
              <span class="trust-num">100%</span>
              <span class="trust-label">Garansi Struktur</span>
            </div>
          </div>
        </div>

        <!-- Right: Modern Showcase Card -->
        <div class="col-lg-6 hero-visual-col">
          <div class="hero-card-frame">
            <div class="hero-media-wrap">
              <img 
                :src="slides[activeSlide].image" 
                :alt="slides[activeSlide].title" 
                class="hero-media-img"
              />
              <div class="hero-media-caption">
                <div class="hero-caption-title">{{ slides[activeSlide].title }}</div>
                <div class="hero-caption-sub">{{ slides[activeSlide].desc }}</div>
              </div>
            </div>

            <!-- Slide Switchers -->
            <div class="hero-slide-switchers">
              <button 
                v-for="(slide, idx) in slides" 
                :key="idx" 
                class="hero-switch-btn" 
                :class="{ 'switch-active': activeSlide === idx }"
                @click="activeSlide = idx"
                type="button"
              >
                {{ slide.tabName }}
              </button>
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
    title: 'Kanopi Kaca Tempered & Rangka Besi',
    desc: 'Struktur rangka hollow galvanis kokoh dengan atap kaca tempered SNI tahan benturan dan cuaca ekstrem.',
    image: '/images/chico/atap 1.jpg'
  },
  {
    tabName: 'Pagar Minimalis',
    title: 'Pagar Besi Hollow Galvanis Modern',
    desc: 'Desain minimalis elegan dengan pelapisan cat anti-karat tahan panas hujan di Medan.',
    image: '/images/chico/pagar 1.jpg'
  },
  {
    tabName: 'Partisi Shower',
    title: 'Partisi Kaca Shower Tempered',
    desc: 'Kaca tempered 10mm dengan aksesoris engsel & handle stainless SUS 304 anti-karat basah.',
    image: '/images/chico/shower 2.webp'
  }
]
</script>

<style scoped>
.hero-section {
  position: relative;
  background-color: var(--background);
  padding: 80px 0 85px;
  border-bottom: 1px solid var(--border);
  overflow: hidden;
}

@media (max-width: 991px) {
  .hero-section {
    padding: 50px 0 55px;
  }
}

.hero-grid {
  row-gap: 40px;
}

.hero-category-text {
  font-family: var(--font-sans), sans-serif;
  font-size: 13px;
  font-weight: 600;
  color: var(--primary);
  letter-spacing: 0.5px;
  text-transform: uppercase;
  margin-bottom: 14px;
}

.hero-title {
  color: var(--foreground);
  font-weight: 800;
  font-size: clamp(26px, 3.4vw, 42px);
  line-height: 1.25;
  letter-spacing: -0.03em;
  margin-bottom: 18px;
}

.hero-lead {
  color: var(--muted-foreground);
  font-size: 15.5px;
  line-height: 1.65;
  margin-bottom: 30px;
  max-width: 530px;
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 12px;
  margin-bottom: 36px;
}

.hero-btn-main,
.hero-btn-sub {
  white-space: nowrap;
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
    flex-direction: column;
    gap: 10px;
    margin-bottom: 30px;
  }

  .hero-btn-main,
  .hero-btn-sub {
    width: 100%;
    max-width: 290px;
    margin: 0 auto;
    justify-content: center;
  }
}

/* Trust Strip: Responsive 3-Column Clean Layout */
.hero-trust-strip {
  display: grid;
  grid-template-columns: 1fr auto 1fr auto 1fr;
  align-items: center;
  gap: 16px;
  padding-top: 24px;
  border-top: 1px solid var(--border);
  text-align: center;
}

@media (max-width: 767px) {
  .hero-trust-strip {
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
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
  font-family: var(--font-sans), sans-serif;
  font-weight: 800;
  font-size: 19px;
  color: var(--primary);
  line-height: 1.2;
}

.trust-label {
  font-size: 11.5px;
  color: var(--muted-foreground);
  margin-top: 3px;
  line-height: 1.35;
  text-align: center;
}

.trust-divider {
  width: 1px;
  height: 28px;
  background: var(--border);
}

/* Right Visual Frame */
.hero-card-frame {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.05), 0 8px 10px -6px rgba(0, 0, 0, 0.02);
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
  transition: opacity 0.3s ease;
}

.hero-media-caption {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 24px 20px 18px;
  background: linear-gradient(180deg, rgba(0, 0, 0, 0) 0%, rgba(23, 23, 23, 0.88) 100%);
  color: #ffffff;
  text-align: left;
}

.hero-caption-title {
  font-family: var(--font-sans), sans-serif;
  font-weight: 700;
  font-size: 15px;
  margin-bottom: 3px;
  color: #ffffff;
}

.hero-caption-sub {
  font-size: 12px;
  color: #e5e5e5;
  line-height: 1.45;
}

.hero-slide-switchers {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  background: var(--muted);
  border-top: 1px solid var(--border);
}

.hero-switch-btn {
  padding: 13px 10px;
  font-family: var(--font-sans), sans-serif;
  font-size: 12px;
  font-weight: 500;
  color: var(--muted-foreground);
  background: transparent;
  border: none;
  cursor: pointer;
  text-align: center;
  transition: all 0.15s ease;
  border-bottom: 2px solid transparent;
}

.hero-switch-btn:hover {
  color: var(--foreground);
  background: var(--card);
}

.switch-active {
  color: var(--primary) !important;
  font-weight: 600 !important;
  background: var(--card) !important;
  border-bottom-color: var(--primary) !important;
}
</style>
