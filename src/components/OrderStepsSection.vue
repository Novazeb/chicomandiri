<template>
  <section class="steps-section section-lg bg-background" id="order-steps">
    <div class="container">
      <div class="section-heading text-center">
        <h2 class="steps-title">
          3 Langkah Mudah Konsultasi &amp; Pemesanan
        </h2>
        <p class="steps-desc">
          Proses cepat, praktis, dan tanpa repot dari awal konsultasi hingga kanopi/pagar terpasang rapi di rumah Anda.
        </p>
      </div>

      <div class="row row-30 justify-content-center steps-grid">
        <!-- Step 1 -->
        <div class="col-md-6 col-lg-4">
          <div class="step-card">
            <div class="step-num-badge">01</div>
            <div class="step-icon-wrap">
              <span class="fa-solid fa-camera-retro"></span>
            </div>
            <h3 class="step-card-title">Kirim Foto Model</h3>
            <p class="step-card-text">
              Kirimkan foto kanopi/pagar yang Anda suka dari Google, Pinterest, atau galeri kami ke WhatsApp kami.
            </p>
          </div>
        </div>

        <!-- Step 2 -->
        <div class="col-md-6 col-lg-4">
          <div class="step-card">
            <div class="step-num-badge">02</div>
            <div class="step-icon-wrap">
              <span class="fa-solid fa-ruler-combined"></span>
            </div>
            <h3 class="step-card-title">Survey Lokasi Gratis</h3>
            <p class="step-card-text">
              Tim kami datang langsung ke rumah Anda di wilayah Medan &amp; sekitarnya untuk ukur detail dan hitung estimasi biaya.
            </p>
          </div>
        </div>

        <!-- Step 3 -->
        <div class="col-md-6 col-lg-4">
          <div class="step-card">
            <div class="step-num-badge">03</div>
            <div class="step-icon-wrap">
              <span class="fa-solid fa-screwdriver-wrench"></span>
            </div>
            <h3 class="step-card-title">Pengerjaan &amp; Garansi</h3>
            <p class="step-card-text">
              Diproduksi rapi dengan besi galvanis tebal pilihan, diantar dan dipasang kokoh sampai selesai bergaransi.
            </p>
          </div>
        </div>
      </div>

      <!-- Action Button -->
      <div class="steps-action-wrap text-center">
        <a 
          class="button button-primary steps-cta-btn" 
          href="https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20pembuatan%20kanopi/pagar" 
          target="_blank" 
          rel="noopener noreferrer"
        >
          <span class="fa-brands fa-whatsapp"></span>
          <span>Konsultasi via WA</span>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.steps-section {
  position: relative;
  background-color: var(--background);
  border-bottom: 1px solid var(--border);
}

.section-heading {
  margin-bottom: 40px;
}

.steps-title {
  color: var(--foreground);
  font-weight: 700;
  font-size: clamp(24px, 3vw, 34px);
  letter-spacing: -0.03em;
  margin-bottom: 8px;
}

.steps-desc {
  color: var(--muted-foreground);
  font-size: 15.5px;
  max-width: 580px;
  line-height: 1.55;
  letter-spacing: -0.01em;
  margin: 0 auto;
}

.steps-grid {
  row-gap: 24px;
}

.step-card {
  position: relative;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-xl);
  padding: 34px 26px;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  box-shadow: var(--shadow-sm);
  transition: transform 0.25s var(--spring-damp), box-shadow 0.25s var(--spring-damp);
}

.step-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-md);
}

.step-num-badge {
  position: absolute;
  top: 18px;
  right: 20px;
  font-family: var(--font-sans);
  font-size: 14px;
  font-weight: 800;
  color: var(--primary);
  opacity: 0.6;
  letter-spacing: -0.02em;
}

.step-icon-wrap {
  width: 58px;
  height: 58px;
  border-radius: 16px;
  background: rgba(0, 113, 227, 0.08);
  color: var(--primary);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
  margin-bottom: 20px;
  transition: transform 0.2s var(--spring-bounce);
}

.step-card:hover .step-icon-wrap {
  transform: scale(1.08);
}

.step-card-title {
  font-family: var(--font-sans);
  font-size: 18px;
  font-weight: 700;
  letter-spacing: -0.02em;
  color: var(--foreground);
  margin-bottom: 10px;
  line-height: 1.3;
}

.step-card-text {
  font-size: 14px;
  color: var(--muted-foreground);
  line-height: 1.55;
  margin: 0;
}

.steps-action-wrap {
  margin-top: 36px;
}

.steps-cta-btn {
  padding: 12px 28px !important;
}
</style>