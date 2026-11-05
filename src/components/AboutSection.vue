<template>
  <section class="about-section section-lg bg-muted" id="about">
    <div class="container">
      <!-- Section Header -->
      <div class="section-heading text-center">
        <h2 class="section-title">
          Keunggulan Layanan Chico Mandiri
        </h2>
        <p class="section-subtitle">
          Standar material dan komitmen pengerjaan yang menjamin kekuatan serta estetika konstruksi rumah Anda.
        </p>
      </div>

      <!-- 3-Column Trust Proposition Cards -->
      <div class="row row-30 justify-content-center trust-grid">
        <!-- Card 1 -->
        <div class="col-md-6 col-lg-4">
          <div class="trust-card">
            <div class="trust-icon-box">
              <span class="fa-solid fa-shield-halved"></span>
            </div>
            <h3 class="trust-card-title">Material Berkualitas SNI</h3>
            <p class="trust-card-desc">
              Menggunakan besi hollow galvanis tebal anti-karat, kaca tempered standar keamanan SNI, dan aksesoris stainless SUS 304 tahan cuaca ekstrem.
            </p>
            <div class="trust-features-wrap">
              <ul class="trust-card-features">
                <li><span class="fa-solid fa-circle-check text-primary"></span>Besi hollow tebal anti-korosi</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Kaca tempered tahan benturan</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Cat epoxy oven tahan cuaca</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Card 2 -->
        <div class="col-md-6 col-lg-4">
          <div class="trust-card">
            <div class="trust-icon-box">
              <span class="fa-solid fa-ruler-combined"></span>
            </div>
            <h3 class="trust-card-title">Gratis Survey Lokasi</h3>
            <p class="trust-card-desc">
              Layanan ukur langsung ke rumah dan konsultasi desain gratis tanpa dipungut biaya untuk area Medan, Deli Serdang, dan sekitarnya.
            </p>
            <div class="trust-features-wrap">
              <ul class="trust-card-features">
                <li><span class="fa-solid fa-circle-check text-primary"></span>Pengukuran presisi di lokasi</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Konsultasi pemilihan material</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Estimasi biaya transparan</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- Card 3 -->
        <div class="col-md-6 col-lg-4">
          <div class="trust-card">
            <div class="trust-icon-box">
              <span class="fa-solid fa-certificate"></span>
            </div>
            <h3 class="trust-card-title">Garansi Resmi Struktur</h3>
            <p class="trust-card-desc">
              Jaminan kekuatan sambungan las presisi, kekokohan rangka, dan kerapian finishing dengan garansi resmi bengkel.
            </p>
            <div class="trust-features-wrap">
              <ul class="trust-card-features">
                <li><span class="fa-solid fa-circle-check text-primary"></span>Teknisi welder berpengalaman</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Sambungan las rapat &amp; halus</li>
                <li><span class="fa-solid fa-circle-check text-primary"></span>Jaminan kepuasan hasil akhir</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <!-- Action Banner (§12 Materials & Depth) -->
      <div class="trust-cta-banner">
        <div class="row align-items-center justify-content-between">
          <div class="col-lg-8 text-center text-lg-left mb-3 mb-lg-0">
            <h4 class="cta-banner-title">Butuh Pengukuran Kanopi, Pagar, atau Partisi Kaca?</h4>
            <p class="cta-banner-desc">Jadwalkan survey gratis langsung ke rumah Anda di wilayah Medan &amp; Deli Serdang.</p>
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
  margin-bottom: 44px;
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
  line-height: 1.6;
  letter-spacing: -0.01em;
}

.trust-grid {
  row-gap: 24px;
}

.trust-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 34px 28px;
  height: 100%;
  display: flex;
  flex-direction: column;
  text-align: center;
  align-items: center;
  transition: transform 0.25s var(--spring-damp), box-shadow 0.25s var(--spring-damp), border-color 0.2s ease;
  box-shadow: var(--shadow-sm);
}

.trust-card:hover {
  border-color: rgba(0, 0, 0, 0.12);
  transform: translateY(-3px);
  box-shadow: var(--shadow-md);
}

/* Centered Icon Container with Apple Soft Blue Accent (§12) */
.trust-icon-box {
  width: 52px;
  height: 52px;
  border-radius: 14px;
  background: rgba(0, 113, 227, 0.08);
  color: var(--primary);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  margin: 0 auto 20px;
  transition: transform 0.2s var(--spring-fast);
}

.trust-card:hover .trust-icon-box {
  transform: scale(1.05);
}

.trust-card-title {
  font-family: var(--font-sans);
  font-size: 17.5px;
  font-weight: 700;
  letter-spacing: -0.02em;
  color: var(--foreground);
  margin-bottom: 10px;
  line-height: 1.3;
  text-align: center;
}

.trust-card-desc {
  font-size: 14px;
  line-height: 1.6;
  letter-spacing: -0.01em;
  color: var(--muted-foreground);
  margin-bottom: 22px;
  text-align: center;
}

.trust-features-wrap {
  width: 100%;
  margin-top: auto;
  padding-top: 18px;
  border-top: 1px solid var(--border);
  display: flex;
  justify-content: center;
}

.trust-card-features {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 9px;
  text-align: left;
}

.trust-card-features li {
  font-size: 13px;
  letter-spacing: -0.01em;
  color: var(--secondary-foreground);
  display: flex;
  align-items: center;
  gap: 9px;
}

/* Bottom CTA Banner with Apple Refined Depth (§12) */
.trust-cta-banner {
  margin-top: 44px;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 28px 32px;
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
