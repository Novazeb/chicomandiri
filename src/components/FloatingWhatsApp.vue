<template>
  <aside class="floating-wa-wrap" aria-label="WhatsApp Floating Action">
    <a 
      href="https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20tanya%20pembuatan%20kanopi/pagar" 
      target="_blank" 
      rel="noopener noreferrer"
      class="floating-wa-btn"
      aria-label="Konsultasi via WhatsApp"
    >
      <span class="fa-brands fa-whatsapp wa-icon"></span>
      <span class="wa-label">Konsultasi via WA</span>
    </a>
  </aside>
</template>

<script setup>
</script>

<style scoped>
.floating-wa-wrap {
  position: fixed;
  bottom: 22px;
  right: 20px;
  z-index: 1090;
}

.floating-wa-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background-color: #25d366;
  color: #ffffff !important;
  font-family: var(--font-sans);
  font-weight: 600;
  font-size: 13.5px;
  letter-spacing: -0.01em;
  padding: 10px 18px 10px 14px;
  border-radius: var(--radius-full);
  box-shadow: 0 4px 16px rgba(37, 211, 102, 0.4), 0 2px 6px rgba(0, 0, 0, 0.1);
  text-decoration: none !important;
  transition: transform 0.2s var(--spring-damp), box-shadow 0.2s var(--spring-damp);
}

.floating-wa-btn:hover {
  transform: translateY(-2px) scale(1.02);
  box-shadow: 0 6px 20px rgba(37, 211, 102, 0.5);
  color: #ffffff !important;
}

.floating-wa-btn:active {
  transform: scale(0.95);
  transition: transform 100ms var(--spring-fast);
}

.wa-icon {
  font-size: 20px;
  line-height: 1;
}

@media (max-width: 575px) {
  .floating-wa-wrap {
    bottom: 18px;
    right: 16px;
  }

  .floating-wa-btn {
    padding: 9px 15px 9px 13px;
    font-size: 12.5px;
  }

  .wa-icon {
    font-size: 18px;
  }
}
</style>