<template>
  <section class="services-section section-xl bg-background" id="services">
    <div class="container">
      <!-- Section Heading -->
      <div class="services-heading text-center">
        <h2 class="services-title">
          Layanan Spesialis Bengkel Kami
        </h2>
        <p class="services-desc">
          Empat pilar keahlian utama Bengkel Las Chico Mandiri dengan standar material terbaik dan pengelasan presisi di Medan.
        </p>
      </div>

      <!-- Service Category Tabs (Clean Segmented Control) -->
      <div class="service-tabs-wrapper">
        <div class="service-tabs-nav">
          <button 
            v-for="service in services" 
            :key="service.id" 
            class="service-tab-btn"
            :class="{ 'tab-active': activeTab === service.id }"
            @click="activeTab = service.id"
            type="button"
          >
            <span :class="['tab-icon', service.icon]"></span>
            <span class="tab-label">{{ service.name }}</span>
          </button>
        </div>
      </div>

      <!-- Active Service Content Showcase -->
      <div class="service-display-card">
        <div class="row align-items-center service-card-grid">
          <!-- Text Details (Left) -->
          <div class="col-lg-6 service-info-col">
            <p class="service-pillar-text">
              {{ currentService.pillar }}
            </p>

            <h3 class="service-content-title">
              {{ currentService.title }}
            </h3>

            <p class="service-lead-text">
              {{ currentService.lead }}
            </p>

            <p class="service-detail-text">
              {{ currentService.description }}
            </p>

            <div class="service-specs-box">
              <div class="service-spec-item" v-for="(spec, sIdx) in currentService.specs" :key="sIdx">
                <span class="fa-solid fa-circle-check text-primary"></span>
                <span>{{ spec }}</span>
              </div>
            </div>

            <div class="service-action-wrap">
              <a 
                class="button button-primary service-cta-btn" 
                :href="currentService.waLink" 
                target="_blank" 
                rel="noopener noreferrer"
              >
                <span class="fa-brands fa-whatsapp"></span>
                <span>Konsultasi via WA</span>
              </a>
            </div>
          </div>

          <!-- Image Display (Right) -->
          <div class="col-lg-6 service-media-col">
            <div class="service-image-frame">
              <img 
                :src="currentService.image" 
                :alt="currentService.name"
                class="service-photo"
              />
              <div class="service-photo-caption">
                <span class="fa-solid fa-camera text-primary" style="margin-right: 6px;"></span>
                {{ currentService.caption }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const activeTab = ref('metal')

const services = [
  {
    id: 'metal',
    name: 'Metal Works',
    icon: 'fa-solid fa-hammer',
    pillar: 'Pilar Layanan: Metal Works',
    title: 'Pagar Minimalis & Kanopi Besi Galvanis',
    lead: 'Pembuatan pagar minimalis, kanopi besi hollow galvanis anti-karat, dan konstruksi besi kokoh.',
    description: 'Dikerjakan langsung oleh teknisi las berpengalaman dengan sambungan las presisi, ketebalan besi standar konstruksi, dan pelapisan cat epoxy anti-karat tahan cuaca panas dan hujan di Medan & Deli Serdang.',
    specs: [
      'Besi hollow galvanis tebal standar SNI anti-karat',
      'Sambungan las rapi, kokoh, dan dihaluskan presisi',
      'Finishing cat epoxy oven tahan gores & cuaca tropis'
    ],
    image: '/images/chico/pagar 1.jpg',
    caption: 'Proyek Pagar Minimalis Besi Hollow Galvanis (Medan)',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20layanan%20Metal%20Works%20(Pagar/Kanopi)'
  },
  {
    id: 'aluminium',
    name: 'Alumunium',
    icon: 'fa-solid fa-door-open',
    pillar: 'Pilar Layanan: Alumunium',
    title: 'Kusen Aluminium & Pintu Sliding Presisi',
    lead: 'Kusen aluminium modern, pintu geser (sliding door), dan partisi jendela presisi.',
    description: 'Pengerjaan pintu dorong dan partisi aluminium modern yang ringan, anti-rayap, tidak berkarat, dan tahan air. Dilengkapi sistem roda bearing berkualitas tinggi yang halus dan awet untuk ruko maupun rumah tinggal.',
    specs: [
      'Bahan aluminium premium anti-rayap & anti-lapuk',
      'Roda bearing presisi halus tanpa suara gesekan',
      'Kerapatan sambungan kedap air dan peredam debu'
    ],
    image: '/images/chico/pintu 1.webp',
    caption: 'Proyek Pintu Sliding Presisi & Kusen Aluminium (Medan)',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20layanan%20Alumunium%20(Pintu%20Sliding/Kusen)'
  },
  {
    id: 'glass',
    name: 'Glass (Kaca)',
    icon: 'fa-solid fa-bath',
    pillar: 'Pilar Layanan: Glass & Tempered',
    title: 'Kanopi Kaca Tempered & Partisi Shower',
    lead: 'Kanopi kaca tempered mewah tahan cuaca ekstrem dan partisi kaca shower kamar mandi.',
    description: 'Diferensiasi mahal Bengkel Las Chico Mandiri. Kami menggunakan kaca tempered berstandar keamanan SNI dengan ketebalan 8mm - 12mm serta fitting engsel dan handle stainless SUS 304 anti-karat untuk estetika kamar mandi dan fasad mewah.',
    specs: [
      'Kaca tempered standar SNI aman & tahan benturan tinggi',
      'Hardware engsel & handle stainless SUS 304 anti-karat basah',
      'Seal karet kedap air presisi mencegah rembesan'
    ],
    image: '/images/chico/shower 2.webp',
    caption: 'Proyek Partisi Kaca Shower Tempered SNI (Medan)',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20layanan%20Glass%20(Kanopi%20Kaca/Shower)'
  },
  {
    id: 'laser',
    name: 'Laser Cutting Art',
    icon: 'fa-solid fa-shapes',
    pillar: 'Pilar Layanan: Laser Cutting Art',
    title: 'Pagar Artistik & Fasad Ornamen Plat Besi',
    lead: 'Pagar motif artistik cutting laser, fasad ornamen plat besi modern, dan dekorasi eksterior premium.',
    description: 'Pemotongan presisi komputerisasi dengan motif kustom geometris, floral, atau minimalis modern. Meningkatkan nilai prestise dan kemewahan arsitektur hunian Anda dengan ketahanan material jangka panjang.',
    specs: [
      'Pemotongan plat besi computerized CNC presisi tinggi',
      'Pilihan motif kustom sesuai selera & desain arsitektur',
      'Pelapisan cat anti-karat melindungi setiap lekuk motif'
    ],
    image: '/images/chico/pagar 3.webp',
    caption: 'Proyek Pagar Ornamen Plat Laser Cutting (Medan)',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20layanan%20Laser%20Cutting%20Art'
  }
]

const currentService = computed(() => {
  return services.find(s => s.id === activeTab.value) || services[0]
})
</script>

<style scoped>
.services-section {
  position: relative;
  background-color: var(--background);
  border-bottom: 1px solid var(--border);
}

.services-heading {
  margin-bottom: 36px;
}

.services-title {
  color: var(--foreground);
  font-weight: 800;
  font-size: clamp(24px, 2.8vw, 32px);
  margin-bottom: 8px;
}

.services-desc {
  color: var(--muted-foreground);
  font-size: 15px;
  max-width: 600px;
  line-height: 1.6;
  margin: 0 auto;
}

/* Category Navigation Tabs (Clean Segmented Control) */
.service-tabs-wrapper {
  max-width: 780px;
  margin: 0 auto 30px;
}

.service-tabs-nav {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 6px;
  background: var(--secondary);
  padding: 6px;
  border-radius: calc(var(--radius) + 2px);
  border: 1px solid var(--border);
}

@media (min-width: 768px) {
  .service-tabs-nav {
    grid-template-columns: repeat(4, 1fr);
  }
}

.service-tab-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  padding: 11px 10px;
  background: transparent;
  border: 1px solid transparent;
  border-radius: var(--radius);
  color: var(--muted-foreground);
  cursor: pointer;
  transition: all 0.15s ease;
  outline: none;
  text-align: center;
}

.service-tab-btn:hover {
  color: var(--foreground);
}

.tab-active {
  background: var(--card) !important;
  border-color: var(--border) !important;
  color: var(--primary) !important;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.08) !important;
  font-weight: 600;
}

.tab-icon {
  font-size: 14px;
}

.tab-label {
  font-family: var(--font-sans), sans-serif;
  font-size: 13px;
  font-weight: 600;
}

/* Service Card Showcase */
.service-display-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 34px 30px;
  box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.04);
}

@media (min-width: 992px) {
  .service-display-card {
    padding: 40px 38px;
  }
}

.service-card-grid {
  row-gap: 28px;
}

.service-info-col {
  display: flex;
  flex-direction: column;
}

@media (min-width: 992px) {
  .service-info-col {
    padding-right: 25px;
  }
}

.service-pillar-text {
  font-family: var(--font-sans), sans-serif;
  font-size: 12.5px;
  font-weight: 600;
  letter-spacing: 0.5px;
  color: var(--primary);
  text-transform: uppercase;
  margin-bottom: 8px;
}

.service-content-title {
  color: var(--foreground);
  font-size: clamp(20px, 2.2vw, 26px);
  font-weight: 800;
  line-height: 1.3;
  margin-bottom: 10px;
}

.service-lead-text {
  color: var(--secondary-foreground);
  font-size: 14.5px;
  font-weight: 500;
  line-height: 1.6;
  margin-bottom: 10px;
}

.service-detail-text {
  color: var(--muted-foreground);
  font-size: 13.5px;
  line-height: 1.65;
  margin-bottom: 20px;
}

.service-specs-box {
  display: flex;
  flex-direction: column;
  gap: 9px;
  margin-bottom: 24px;
  padding: 14px 16px;
  background: var(--muted);
  border: 1px solid var(--border);
  border-radius: var(--radius);
}

.service-spec-item {
  font-size: 13px;
  color: var(--foreground);
  display: flex;
  align-items: center;
  gap: 9px;
}

.service-action-wrap {
  margin-top: auto;
}

.service-cta-btn {
  white-space: nowrap;
}

@media (max-width: 767px) {
  .service-info-col {
    text-align: center;
  }

  .service-pillar-text {
    text-align: center;
  }

  .service-content-title {
    text-align: center;
  }

  .service-lead-text {
    text-align: center;
  }

  .service-detail-text {
    text-align: center;
  }

  .service-specs-box {
    text-align: left;
    max-width: 360px;
    margin-left: auto;
    margin-right: auto;
  }

  .service-action-wrap {
    display: flex;
    justify-content: center;
  }

  .service-cta-btn {
    width: 100%;
    max-width: 290px;
    margin: 0 auto;
    justify-content: center;
  }
}

/* Right Image Frame */
.service-image-frame {
  position: relative;
  width: 100%;
  height: 330px;
  border-radius: 10px;
  overflow: hidden;
  background: var(--secondary);
  border: 1px solid var(--border);
}

@media (min-width: 992px) {
  .service-image-frame {
    height: 380px;
  }
}

.service-photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.service-photo-caption {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 10px 14px;
  background: rgba(255, 255, 255, 0.95);
  color: var(--foreground);
  font-size: 12px;
  font-weight: 500;
  border-top: 1px solid var(--border);
}
</style>
