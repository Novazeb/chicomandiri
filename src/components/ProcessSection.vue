<template>
  <section class="services-section section-xl bg-background" id="services">
    <div class="container">
      <!-- Section Heading: Visual-first, Concise -->
      <div class="services-heading text-center">
        <h2 class="services-title">
          Katalog Layanan &amp; Produk Kami
        </h2>
        <p class="services-desc">
          Pengerjaan presisi dengan material pilihan untuk rumah, ruko, dan kantor di wilayah Medan &amp; sekitarnya.
        </p>
      </div>

      <!-- 4-Card Visual Catalog Grid -->
      <div class="row row-30 services-grid">
        <div 
          v-for="service in services" 
          :key="service.id" 
          class="col-md-6 col-lg-6 service-col"
        >
          <div class="service-card">
            <!-- Large Project Photo -->
            <div class="service-photo-wrap">
              <img 
                :src="service.image" 
                :alt="service.title" 
                class="service-photo"
              />
              <span class="service-badge-pill">{{ service.badge }}</span>
              <div class="service-photo-tag">
                <span class="fa-solid fa-camera text-primary"></span>
                <span>{{ service.photoTag }}</span>
              </div>
            </div>

            <!-- Card Content: Fast to scan, zero wall of text -->
            <div class="service-content">
              <h3 class="service-card-title">{{ service.title }}</h3>
              <p class="service-card-summary">{{ service.summary }}</p>

              <ul class="service-bullet-list">
                <li v-for="(spec, sIdx) in service.specs" :key="sIdx">
                  <span class="fa-solid fa-circle-check text-primary"></span>
                  <span>{{ spec }}</span>
                </li>
              </ul>

              <div class="service-card-action">
                <a 
                  class="button button-primary service-wa-btn" 
                  :href="service.waLink" 
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
    </div>
  </section>
</template>

<script setup>
const services = [
  {
    id: 'kanopi',
    title: 'Kanopi Kaca Tempered & Rangka Besi',
    badge: 'Paling Diminati',
    photoTag: 'Carport & Teras',
    summary: 'Atap kanopi mewah anti-panas dan anti-bocor untuk carport dan teras.',
    specs: [
      'Kaca tempered tebal 8mm – 12mm standar SNI',
      'Rangka hollow galvanis anti-karat bergaransi',
      'Pilihan model gantung minimalis atau bertiang'
    ],
    image: '/images/chico/atap 1.jpg',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20tanya%20pembuatan%20Kanopi%20Kaca%20Tempered'
  },
  {
    id: 'pagar',
    title: 'Pagar & Gerbang Minimalis Modern',
    badge: 'Besi Galvanis',
    photoTag: 'Pagar & Gerbang',
    summary: 'Pagar kokoh penunjang keamanan dan keindahan fasad rumah Anda.',
    specs: [
      'Besi hollow galvanis tebal & tahan karat cuaca Medan',
      'Model kisi-kisi minimalis, plat perforated & laser cutting',
      'Finishing cat epoxy oven tahan gores & anti-pudar'
    ],
    image: '/images/chico/pagar 1.jpg',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20tanya%20pembuatan%20Pagar%20Minimalis'
  },
  {
    id: 'pintu',
    title: 'Pintu Sliding & Lipat Aluminium',
    badge: 'Hemat Tempat',
    photoTag: 'Pintu & Penyekat',
    summary: 'Pintu geser modern kedap suara dan anti-rayap untuk ruko dan rumah.',
    specs: [
      'Profil aluminium premium ringan, kuat & anti-karat',
      'Sistem roda bearing presisi geser halus tanpa suara',
      'Pilihan kaca bening, riben (gelap), buram, atau kombinasi'
    ],
    image: '/images/chico/pintu 1.webp',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20tanya%20pembuatan%20Pintu%20Sliding%20Aluminium'
  },
  {
    id: 'shower',
    title: 'Partisi Kaca & Shower Box Tempered',
    badge: 'Mewah & Estetik',
    photoTag: 'Kamar Mandi',
    summary: 'Penyekat kaca kamar mandi agar area tetap kering, bersih, dan mewah.',
    specs: [
      'Kaca tempered 10mm aman dengan tepi beveled halus',
      'Engsel & handle stainless SUS 304 tahan karat basah',
      'Kamar mandi tetap kering, bersih, dan tampak luas'
    ],
    image: '/images/chico/shower 1.jpg',
    waLink: 'https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20tanya%20pembuatan%20Partisi%20Kaca%20Shower'
  }
]
</script>

<style scoped>
.services-section {
  position: relative;
  background-color: var(--background);
  border-bottom: 1px solid var(--border);
}

.services-heading {
  margin-bottom: 42px;
}

.services-title {
  color: var(--foreground);
  font-weight: 700;
  font-size: clamp(24px, 3vw, 34px);
  letter-spacing: -0.03em;
  margin-bottom: 8px;
}

.services-desc {
  color: var(--muted-foreground);
  font-size: 15.5px;
  max-width: 580px;
  line-height: 1.55;
  letter-spacing: -0.01em;
  margin: 0 auto;
}

.services-grid {
  row-gap: 28px;
}

/* Service Card: Apple Squircle + Visual-first */
.service-card {
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

.service-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-md);
}

.service-photo-wrap {
  position: relative;
  width: 100%;
  height: 240px;
  background: var(--secondary);
  overflow: hidden;
}

@media (min-width: 1200px) {
  .service-photo-wrap {
    height: 270px;
  }
}

.service-photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.6s var(--spring-damp);
}

.service-card:hover .service-photo {
  transform: scale(1.04);
}

.service-badge-pill {
  position: absolute;
  top: 14px;
  left: 14px;
  padding: 5px 12px;
  background: rgba(255, 255, 255, 0.92);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border-radius: var(--radius-full);
  font-size: 11px;
  font-weight: 700;
  color: var(--foreground);
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.12);
}

.service-photo-tag {
  position: absolute;
  bottom: 12px;
  right: 14px;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 4px 10px;
  background: rgba(29, 29, 31, 0.82);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  border-radius: var(--radius-full);
  font-size: 11px;
  font-weight: 600;
  color: #ffffff;
}

.service-content {
  padding: 26px 24px;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.service-card-title {
  font-family: var(--font-sans);
  font-size: 18.5px;
  font-weight: 700;
  letter-spacing: -0.02em;
  color: var(--foreground);
  margin-bottom: 6px;
  line-height: 1.25;
}

.service-card-summary {
  font-size: 13.5px;
  color: var(--muted-foreground);
  line-height: 1.5;
  margin-bottom: 16px;
}

.service-bullet-list {
  list-style: none;
  padding: 0;
  margin: 0 0 22px 0;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.service-bullet-list li {
  font-size: 13.5px;
  color: var(--secondary-foreground);
  display: flex;
  align-items: flex-start;
  gap: 9px;
  line-height: 1.4;
}

.service-bullet-list li .fa-circle-check {
  margin-top: 3px;
  font-size: 13px;
  flex-shrink: 0;
}

.service-card-action {
  margin-top: auto;
  padding-top: 10px;
}

.service-wa-btn {
  width: 100%;
  justify-content: center;
}
</style>