<template>
  <section class="contact-section section-xl bg-background" id="contacts">
    <div class="container">
      <div class="row align-items-stretch contact-grid">
        <!-- Left: Workshop Details & Credibility -->
        <div class="col-lg-6 contact-info-col">
          <div class="workshop-card">
            <div class="workshop-photo-wrap">
              <img 
                src="/images/chico/workshop-las.jpg" 
                alt="Workshop Bengkel Las Chico Mandiri" 
                class="workshop-photo"
              />
            </div>

            <div class="workshop-content">
              <div class="workshop-header-wrap">
                <h3 class="workshop-title">
                  Bengkel Las Chico Mandiri
                </h3>
                <p class="workshop-tagline">
                  Metal Works, Alumunium, Glass, Laser Cutting Art
                </p>
              </div>

              <div class="workshop-meta-list">
                <div class="workshop-meta-item">
                  <div class="meta-icon"><span class="fa-solid fa-location-dot"></span></div>
                  <div class="meta-text">
                    <strong>Alamat Workshop:</strong><br>
                    Jl. Roso No. 8, Deli Tua – Marendal, Medan
                  </div>
                </div>

                <div class="workshop-meta-item">
                  <div class="meta-icon"><span class="fa-solid fa-map-location-dot"></span></div>
                  <div class="meta-text">
                    <strong>Wilayah Layanan:</strong><br>
                    Medan, Deli Serdang, dan sekitarnya (Gratis Survey Lokasi)
                  </div>
                </div>

                <div class="workshop-meta-item">
                  <div class="meta-icon"><span class="fa-brands fa-whatsapp"></span></div>
                  <div class="meta-text">
                    <strong>WhatsApp Resmi:</strong><br>
                    <a href="https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20pembuatan%20kanopi/pagar" target="_blank" rel="noopener noreferrer" class="meta-link">
                      0813-7693-3039
                    </a>
                  </div>
                </div>

                <div class="workshop-meta-item">
                  <div class="meta-icon"><span class="fa-regular fa-clock"></span></div>
                  <div class="meta-text">
                    <strong>Jam Operasional:</strong><br>
                    Senin – Sabtu (08.00 – 17.30 WIB)
                  </div>
                </div>
              </div>

              <div class="workshop-actions">
                <a 
                  href="https://maps.google.com/?q=Jl.+Roso+No.+8,+Deli+Tua+-+Marendal,+Medan" 
                  target="_blank" 
                  rel="noopener noreferrer" 
                  class="button button-primary-outline w-100"
                >
                  <span class="fa-solid fa-arrow-up-right-from-square" style="margin-right: 8px;"></span>
                  <span>Buka Titik Lokasi di Maps</span>
                </a>
              </div>
            </div>
          </div>
        </div>

        <!-- Right: Quotation / Survey Request Form -->
        <div class="col-lg-6 contact-form-col">
          <div class="form-container-card">
            <div class="form-header-wrap">
              <h3 class="form-card-title">
                Konsultasi &amp; Estimasi Biaya
              </h3>
              <p class="form-card-subtitle">
                Isi data rencana pengerjaan di bawah. Pesan akan terformat otomatis dan langsung terhubung ke WhatsApp kami.
              </p>
            </div>

            <form @submit.prevent="submitContactToWa">
              <div class="form-wrap">
                <label class="form-label" for="contact-name">Nama Lengkap</label>
                <input 
                  class="form-input" 
                  id="contact-name" 
                  type="text" 
                  v-model="cForm.name" 
                  placeholder="Contoh: Bpk. Budi Santoso" 
                  required
                />
              </div>

              <div class="form-wrap">
                <label class="form-label" for="contact-phone">Nomor HP / WhatsApp</label>
                <input 
                  class="form-input" 
                  id="contact-phone" 
                  type="tel" 
                  v-model="cForm.phone" 
                  placeholder="Contoh: 0812xxxxxxxx" 
                  required
                />
              </div>

              <div class="form-wrap">
                <label class="form-label" for="contact-location">Area / Alamat Rumah di Medan</label>
                <input 
                  class="form-input" 
                  id="contact-location" 
                  type="text" 
                  v-model="cForm.location" 
                  placeholder="Contoh: Komplek Tasbi / Marendal / Johor" 
                  required
                />
              </div>

              <div class="form-wrap">
                <label class="form-label" for="contact-service">Rencana Pengerjaan</label>
                <input 
                  class="form-input" 
                  id="contact-service" 
                  type="text" 
                  v-model="cForm.service" 
                  placeholder="Contoh: Kanopi kaca tempered 4x6m & pagar minimalis" 
                  required
                />
              </div>

              <div class="form-submit-wrap">
                <button class="button button-primary form-submit-btn" type="submit">
                  <span class="fa-brands fa-whatsapp"></span>
                  <span>Konsultasi via WA</span>
                </button>
              </div>

              <div class="form-guarantee-note">
                <span class="fa-solid fa-lock text-primary" style="margin-right: 6px;"></span>
                Konsultasi &amp; survey gratis tanpa ikatan biaya.
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive } from 'vue'

const cForm = reactive({
  name: '',
  phone: '',
  location: '',
  service: ''
})

function submitContactToWa() {
  const name = cForm.name.trim() || 'Pelanggan'
  const phone = cForm.phone.trim() || '-'
  const loc = cForm.location.trim() || 'Medan'
  const srv = cForm.service.trim() || 'Kanopi / Pagar / Kaca'

  const message = `Halo Bengkel Las Chico Mandiri, saya ${name} (${phone}) dari ${loc}. Saya tertarik konsultasi pembuatan: ${srv}. Mohon info jadwal survey gratis ke lokasi.`
  
  const waUrl = `https://wa.me/6281376933039?text=${encodeURIComponent(message)}`
  window.open(waUrl, '_blank')
}
</script>

<style scoped>
.contact-section {
  position: relative;
  background-color: var(--background);
  border-bottom: 1px solid var(--border);
}

.contact-grid {
  row-gap: 28px;
}

/* Left Workshop Card - Apple Squircle & Ambient Depth */
.workshop-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-xl);
  overflow: hidden;
  height: 100%;
  display: flex;
  flex-direction: column;
  box-shadow: var(--shadow-sm);
  transition: box-shadow 0.3s var(--spring-damp), transform 0.3s var(--spring-damp);
}

.workshop-card:hover {
  box-shadow: var(--shadow-md);
}

.workshop-photo-wrap {
  width: 100%;
  height: 230px;
  overflow: hidden;
  background: var(--secondary);
  position: relative;
}

.workshop-photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.6s var(--spring-damp);
}

.workshop-card:hover .workshop-photo {
  transform: scale(1.03);
}

.workshop-content {
  padding: 32px 28px;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.workshop-header-wrap {
  text-align: center;
  margin-bottom: 24px;
}

.workshop-title {
  color: var(--foreground);
  font-size: 21px;
  font-weight: 700;
  letter-spacing: -0.025em;
  line-height: 1.25;
  margin-bottom: 6px;
  text-align: center;
}

.workshop-tagline {
  color: var(--primary);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  margin-bottom: 0;
  text-align: center;
}

.workshop-meta-list {
  display: flex;
  flex-direction: column;
  gap: 22px;
  margin-bottom: 28px;
}

.workshop-meta-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 10px;
}

.meta-icon {
  width: 46px;
  height: 46px;
  min-width: 46px;
  border-radius: 14px;
  background: rgba(0, 113, 227, 0.08);
  color: var(--primary);
  border: 1px solid rgba(0, 113, 227, 0.16);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 17px;
  margin: 0 auto;
  transition: transform 0.2s var(--spring-bounce);
}

.workshop-meta-item:hover .meta-icon {
  transform: scale(1.08);
}

.meta-text {
  font-size: 13.5px;
  color: var(--muted-foreground);
  line-height: 1.55;
  text-align: center;
  max-width: 380px;
}

.meta-text strong {
  color: var(--foreground);
  display: block;
  font-size: 14px;
  font-weight: 600;
  letter-spacing: -0.01em;
  margin-bottom: 2px;
}

.meta-link {
  color: var(--primary);
  font-weight: 600;
  text-decoration: none;
  transition: opacity 0.15s ease;
}

.meta-link:hover {
  text-decoration: underline;
  opacity: 0.85;
}

.workshop-actions {
  margin-top: auto;
}

/* Right Form Card - Apple Elevated Surface */
.form-container-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: var(--radius-xl);
  padding: 34px 30px;
  height: 100%;
  display: flex;
  flex-direction: column;
  box-shadow: var(--shadow-sm);
  transition: box-shadow 0.3s var(--spring-damp);
}

.form-container-card:hover {
  box-shadow: var(--shadow-md);
}

@media (max-width: 575px) {
  .workshop-content {
    padding: 26px 20px;
  }

  .form-container-card {
    padding: 26px 20px;
  }
}

.form-card-title {
  color: var(--foreground);
  font-size: 21px;
  font-weight: 700;
  letter-spacing: -0.025em;
  line-height: 1.25;
  margin-bottom: 6px;
}

.form-card-subtitle {
  color: var(--muted-foreground);
  font-size: 13.5px;
  line-height: 1.55;
  margin-bottom: 24px;
}

.form-submit-wrap {
  margin-top: 14px;
  margin-bottom: 14px;
}

.form-submit-btn {
  width: 100%;
  justify-content: center;
}

.form-guarantee-note {
  text-align: center;
  font-size: 12px;
  color: var(--muted-foreground);
  display: flex;
  align-items: center;
  justify-content: center;
}

@media (max-width: 767px) {
  .workshop-header-wrap {
    text-align: center;
  }

  .form-header-wrap {
    text-align: center;
  }
}
</style>
