<template>
  <section class="about-section section-lg bg-muted" id="about">
    <div class="container">
      <!-- Section Header: Punchy, Low Text -->
      <div class="section-heading text-center">
        <h2 class="section-title">
          Kenapa Percayakan ke Chico Mandiri?
        </h2>
        <p class="section-subtitle">
          Kualitas material pilihan, tukang las berpengalaman, dan komitmen hasil pengerjaan rapi bergaransi.
        </p>
      </div>

      <!-- 3-Column Visual Photo Proof Cards -->
      <div class="row row-30 justify-content-center trust-grid">
        <!-- Card 1: Material & Workshop -->
        <div class="col-md-6 col-lg-4">
          <div class="trust-card">
            <div class="trust-img-box">
              <img src="/images/chico/workshop-las.jpg" alt="Workshop Las Chico Mandiri" class="trust-photo" />
              <span class="trust-img-pill">Bahan Pilihan SNI</span>
            </div>
            <div class="trust-card-body">
              <h3 class="trust-card-title">Besi Galvanis Anti-Karat</h3>
              <ul class="trust-card-features">
                <li><span class="fa-solid fa-circle-check text-primary"></span>Hollow galvanis tebal standar SNI</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Kaca tempered tahan benturan keras</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Lapisan cat oven anti-karat &amp; cuaca</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Card 2: Free Survey -->
        <div class="col-md-6 col-lg-4">
          <div class="trust-card">
            <div class="trust-img-box">
              <img src="/images/chico/atap 1.jpg" alt="Pemasangan Kanopi di Rumah" class="trust-photo" />
              <span class="trust-img-pill">100% Gratis</span>
            </div>
            <div class="trust-card-body">
              <h3 class="trust-card-title">Gratis Survey &amp; Ukur Lokasi</h3>
              <ul class="trust-card-features">
                <li><span class="fa-solid fa-circle-check text-primary"></span>Langsung datang ke rumah Anda</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Pengukuran presisi &amp; konsultasi model</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Estimasi biaya transparan tanpa biaya tersembunyi</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Card 3: Warranty & Neatness -->
        <div class="col-md-6 col-lg-4">
          <div class="trust-card">
            <div class="trust-img-box">
              <img src="/images/chico/pagar 1.jpg" alt="Pagar Minimalis Rapi" class="trust-photo" />
              <span class="trust-img-pill">Garansi Resmi</span>
            </div>
            <div class="trust-card-body">
              <h3 class="trust-card-title">Pengerjaan Rapi &amp; Bergaransi</h3>
              <ul class="trust-card-features">
                <li><span class="fa-solid fa-circle-check text-primary"></span>Tukang las ahli berpengalaman 10+ thn</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Sambungan las rapat, kokoh, dan halus</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Bisa custom sesuai foto Pinterest / IG</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <!-- Action Banner: Photo Proof CTA (§12) -->
      <div class="trust-cta-banner">
        <div class="row align-items-center justify-content-between">
          <div class="col-lg-8 text-center text-lg-left mb-3 mb-lg-0">
            <h4 class="cta-banner-title">Mau Survey Gratis atau Tanya Perkiraan Biaya?</h4>
            <p class="cta-banner-desc">Kirim ukuran atau contoh model yang Anda inginkan ke WhatsApp kami sekarang.</p>
          </div>
          <div class="col-lg-4 text-center text-lg-right">
            <a 
              class="button button-primary cta-banner-btn" 
              href="https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20ingin%20jadwalkan%20survey%20gratis%20ke%20rumah%20saya" 
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
  </section>
</template>

<script setup>
</script>

<style scoped>
.about-section {
  position: relative;
  background-color: var(--muted);
  border-bottom: 1px solid var(--border);
}

.section-heading {
  margin-bottom: 38px;
}

.section-title {
  color: var(--foreground);
  font-weight: 700;
  font-size: clamp(24px, 3vw, 34px);
  letter-spacing: -0.03em;
  margin-bottom: 8px;
}

.section-subtitle {
  color: var(--muted-foreground);
  font-size: 15.5px;
  max-width: 580px;
  margin: 0 auto;
  line-height: 1.55;
  letter-spacing: -0.01em;
}

.trust-grid {
  row-gap: 24px;
}

/* Visual Photo Proof Cards */
.trust-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-xl);
  overflow: hidden;
  height: 100%;
  display: flex;
  flex-direction: column;
  transition: transform 0.25s var(--spring-damp), box-shadow 0.25s var(--spring-damp);
  box-shadow: var(--shadow-sm);
}

.trust-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-md);
}

.trust-img-box {
  position: relative;
  width: 100%;
  height: 190px;
  background: var(--secondary);
  overflow: hidden;
}

.trust-photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.5s var(--spring-damp);
}

.trust-card:hover .trust-photo {
  transform: scale(1.05);
}

.trust-img-pill {
  position: absolute;
  top: 14px;
  left: 14px;
  padding: 5px 12px;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border-radius: var(--radius-full);
  font-size: 11px;
  font-weight: 700;
  color: var(--foreground);
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.12);
  letter-spacing: -0.01em;
}

.trust-card-body {
  padding: 24px 22px;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.trust-card-title {
  font-family: var(--font-sans);
  font-size: 17.5px;
  font-weight: 700;
  letter-spacing: -0.02em;
  color: var(--foreground);
  margin-bottom: 16px;
  line-height: 1.3;
}

.trust-card-features {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 11px;
}

.trust-card-features li {
  font-size: 13.5px;
  letter-spacing: -0.01em;
  color: var(--secondary-foreground);
  display: flex;
  align-items: flex-start;
  gap: 9px;
  line-height: 1.4;
}

.trust-card-features li .fa-circle-check {
  margin-top: 3px;
  font-size: 13px;
  flex-shrink: 0;
}

/* Bottom CTA Banner with Apple Refined Depth (§12) */
.trust-cta-banner {
  margin-top: 40px;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 26px 30px;
  box-shadow: var(--shadow-sm);
  transition: box-shadow 0.25s var(--spring-damp);
}

.trust-cta-banner:hover {
  box-shadow: var(--shadow-md);
}

.cta-banner-title {
  color: var(--foreground);
  font-size: 18px;
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 4px;
}

.cta-banner-desc {
  color: var(--muted-foreground);
  font-size: 14px;
  letter-spacing: -0.01em;
  margin: 0;
}

.cta-banner-btn {
  white-space: nowrap;
}

@media (max-width: 767px) {
  .trust-cta-banner {
    padding: 24px 20px;
    text-align: center;
  }

  .cta-banner-btn {
    width: 100%;
    max-width: 280px;
    margin: 14px auto 0;
  }
}
</style>
