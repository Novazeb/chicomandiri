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
  padding: 40px 0 36px;
  border-top: 1px solid var(--border);
  color: var(--foreground);
}

.footer-brand {
  gap: 12px;
  text-decoration: none;
  margin-bottom: 22px;
}

.footer-logo-img {
  width: 40px;
  height: 40px;
  object-fit: contain;
  border-radius: var(--radius);
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.06);
}

.footer-brand-title {
  font-family: var(--font-sans), sans-serif;
  font-weight: 800;
  font-size: 16px;
  letter-spacing: -0.01em;
  color: var(--foreground);
  line-height: 1.2;
}

.footer-brand-sub {
  font-family: var(--font-sans), sans-serif;
  font-weight: 600;
  font-size: 9.5px;
  letter-spacing: 0.5px;
  color: var(--primary);
  text-transform: uppercase;
  line-height: 1.2;
  margin-top: 2px;
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
  font-size: 14px;
  color: var(--foreground);
  text-decoration: none;
  transition: color 0.15s ease;
  line-height: 1.5;
}

.footer-wa-link:hover,
.footer-address-link:hover {
  color: var(--primary);
  text-decoration: underline;
}

.footer-wa-link strong,
.footer-address-link strong {
  color: var(--foreground);
}

@media (max-width: 575px) {
  .site-footer {
    padding: 32px 0 28px;
  }

  .footer-wa-link,
  .footer-address-link {
    font-size: 13px;
    text-align: center;
  }
}
</style>
