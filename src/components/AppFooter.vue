<template>
  <footer class="site-footer bg-muted" id="footer">
    <div class="container text-center">
      <a class="footer-brand d-inline-flex align-items-center justify-content-center" href="#home">
        <img src="/images/chico/logo.png" alt="Bengkel Las Chico Mandiri" class="footer-logo-img"/>
        <div class="text-left footer-brand-text">
          <div class="footer-brand-title">CHICO MANDIRI</div>
          <div class="footer-brand-sub">Metal Works &bull; Alumunium &bull; Glass &bull; Laser Cutting Art</div>
        </div>
      </a>

      <!-- Kontak WA & Alamat Saja -->
      <div class="footer-contact-info">
        <div class="footer-contact-item">
          <a class="footer-wa-link" href="https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20pembuatan%20kanopi/pagar" target="_blank" rel="noopener noreferrer">
            <span class="fa-brands fa-whatsapp text-primary"></span>
            <strong>WhatsApp:</strong> 0813-7693-3039
          </a>
        </div>

        <div class="footer-contact-item">
          <a class="footer-address-link" href="https://maps.google.com/?q=Jl.+Roso+No.+8,+Deli+Tua+-+Marendal,+Medan" target="_blank" rel="noopener noreferrer">
            <span class="fa-solid fa-location-dot text-primary"></span>
            <strong>Alamat:</strong> Jl. Roso No. 8, Deli Tua – Marendal, Medan
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
</script>

<style scoped>
.site-footer {
  background-color: var(--muted);
  padding: 48px 0 42px;
  border-top: 1px solid var(--border);
  color: var(--foreground);
}

.footer-brand {
  gap: 12px;
  text-decoration: none;
  margin-bottom: 24px;
  transition: opacity 0.2s var(--spring-damp);
}

.footer-brand:active {
  transform: scale(0.98);
  opacity: 0.8;
}

.footer-logo-img {
  width: 42px;
  height: 42px;
  object-fit: contain;
  border-radius: 12px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.08);
}

.footer-brand-title {
  font-family: var(--font-sans), sans-serif;
  font-weight: 700;
  font-size: 16px;
  letter-spacing: -0.02em;
  color: var(--foreground);
  line-height: 1.2;
}

.footer-brand-sub {
  font-family: var(--font-sans), sans-serif;
  font-weight: 600;
  font-size: 9.5px;
  letter-spacing: 0.06em;
  color: var(--primary);
  text-transform: uppercase;
  line-height: 1.2;
  margin-top: 3px;
}

.footer-contact-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;
}

.footer-contact-item {
  display: flex;
  align-items: center;
  justify-content: center;
}

.footer-wa-link,
.footer-address-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-family: var(--font-sans), sans-serif;
  font-size: 13.5px;
  color: var(--muted-foreground);
  text-decoration: none;
  padding: 6px 14px;
  border-radius: var(--radius-full);
  background: rgba(255, 255, 255, 0.6);
  border: 1px solid var(--border);
  transition: all 0.2s var(--spring-damp);
  line-height: 1.5;
}

.footer-wa-link:hover,
.footer-address-link:hover {
  color: var(--foreground);
  background: #ffffff;
  border-color: rgba(0, 0, 0, 0.16);
  box-shadow: var(--shadow-sm);
}

.footer-wa-link:active,
.footer-address-link:active {
  transform: scale(0.96);
  transition: transform 100ms var(--spring-fast);
}

.footer-wa-link strong,
.footer-address-link strong {
  color: var(--foreground);
  font-weight: 600;
}

@media (max-width: 575px) {
  .site-footer {
    padding: 36px 0 32px;
  }

  .footer-wa-link,
  .footer-address-link {
    font-size: 12.5px;
    padding: 8px 12px;
    width: 100%;
    max-width: 320px;
  }
}
</style>
