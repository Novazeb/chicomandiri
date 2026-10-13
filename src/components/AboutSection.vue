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

      <!-- Action Banner -->
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
  margin-bottom: 40px;
}

.section-title {
  color: var(--foreground);
  font-weight: 800;
  font-size: clamp(24px, 2.8vw, 32px);
  margin-bottom: 8px;
}

.section-subtitle {
  color: var(--muted-foreground);
  font-size: 15px;
  max-width: 580px;
  margin: 0 auto;
  line-height: 1.6;
}

.trust-grid {
  row-gap: 24px;
}

.trust-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 32px 26px;
  height: 100%;
  display: flex;
  flex-direction: column;
  text-align: center;
  align-items: center;
  transition: transform 0.15s ease, border-color 0.15s ease, box-shadow 0.15s ease;
  box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.03);
}

.trust-card:hover {
  border-color: #cbd5e1;
  transform: translateY(-2px);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
}

/* Centered Icon Container with Soft Sky Accent */
.trust-icon-box {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  background: var(--accent);
  color: var(--primary);
  border: 1px solid #bae6fd;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  margin: 0 auto 18px;
}

.trust-card-title {
  font-family: var(--font-sans), sans-serif;
  font-size: 17px;
  font-weight: 700;
  color: var(--foreground);
  margin-bottom: 10px;
  line-height: 1.35;
  text-align: center;
}

.trust-card-desc {
  font-size: 13.5px;
  line-height: 1.6;
  color: var(--muted-foreground);
  margin-bottom: 20px;
  text-align: center;
}

.trust-features-wrap {
  width: 100%;
  margin-top: auto;
  padding-top: 16px;
  border-top: 1px solid var(--secondary);
  display: flex;
  justify-content: center;
}

.trust-card-features {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 8px;
  text-align: left;
}

.trust-card-features li {
  font-size: 13px;
  color: var(--foreground);
  display: flex;
  align-items: center;
  gap: 8px;
}

/* Bottom CTA Banner */
.trust-cta-banner {
  margin-top: 40px;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 26px 30px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.04);
}

.cta-banner-title {
  color: var(--foreground);
  font-size: 17px;
  font-weight: 700;
  margin-bottom: 4px;
}

.cta-banner-desc {
  color: var(--muted-foreground);
  font-size: 13.5px;
  margin: 0;
}

.cta-banner-btn {
  white-space: nowrap;
}

@media (max-width: 767px) {
  .trust-cta-banner {
    padding: 22px 18px;
    text-align: center;
  }

  .cta-banner-btn {
    width: 100%;
    max-width: 280px;
    margin: 12px auto 0;
  }
}
</style>
