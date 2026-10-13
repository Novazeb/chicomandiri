<template>
  <section class="contact-section section-xl bg-background" id="contacts">
    <div class="container">
      <div class="row align-items-stretch contact-grid">
        <!-- Left: Workshop Details & Credibility -->
        <div class="col-lg-6 contact-info-col">
          <div class="workshop-card">
            <div class="workshop-photo-wrap">
              <img 
                src="/images/chico/pintu 1.webp" 
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
                  <span>Kirim Konsultasi via WhatsApp</span>
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

/* Left Workshop Card */
.workshop-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  overflow: hidden;
  height: 100%;
  display: flex;
  flex-direction: column;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.04);
}

.workshop-photo-wrap {
  width: 100%;
  height: 220px;
  overflow: hidden;
  background: var(--secondary);
}

.workshop-photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.workshop-content {
  padding: 30px 26px;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.workshop-header-wrap {
  text-align: center;
}

.workshop-title {
  color: var(--foreground);
  font-size: 20px;
  font-weight: 800;
  margin-bottom: 4px;
  text-align: center;
}

.workshop-tagline {
  color: var(--primary);
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  margin-bottom: 22px;
  text-align: center;
}

.workshop-meta-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin-bottom: 24px;
}

.workshop-meta-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 8px;
}

.meta-icon {
  width: 44px;
  height: 44px;
  min-width: 44px;
  border-radius: var(--radius);
  background: var(--accent);
  color: var(--primary);
  border: 1px solid #bae6fd;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 16px;
  margin: 0 auto;
}

.meta-text {
  font-size: 13.5px;
  color: var(--muted-foreground);
  line-height: 1.55;
  text-align: center;
}

.meta-text strong {
  color: var(--foreground);
  display: block;
  margin-bottom: 2px;
}

.meta-link {
  color: var(--primary);
  font-weight: 600;
  text-decoration: none;
}

.meta-link:hover {
  text-decoration: underline;
}

.workshop-actions {
  margin-top: auto;
}

/* Right Form Card */
.form-container-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 32px 28px;
  height: 100%;
  display: flex;
  flex-direction: column;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.04);
}

@media (max-width: 575px) {
  .form-container-card {
    padding: 26px 20px;
  }
}

.form-card-title {
  color: var(--foreground);
  font-size: 20px;
  font-weight: 800;
  margin-bottom: 4px;
}

.form-card-subtitle {
  color: var(--muted-foreground);
  font-size: 13.5px;
  line-height: 1.6;
  margin-bottom: 22px;
}

.form-submit-wrap {
  margin-top: 10px;
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
