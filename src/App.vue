<template>
  <div>
    <!-- Preloader -->
    <Preloader />

    <div class="page">
      <!-- Header & Navigation -->
      <AppHeader />

      <!-- Section 1: Hero Section (Visual Card & Quick Tabs) -->
      <HeroSection />

      <!-- Section 2: Keunggulan dengan Bukti Foto Riil -->
      <AboutSection />

      <!-- Section 3: Katalog Layanan (4 Kartu Bergambar Lengkap) -->
      <ProcessSection />

      <!-- Section 4: Galeri Foto Proyek Asli & Filter Kategori -->
      <PortfolioSection />

      <!-- Section 5: 3 Langkah Mudah Konsultasi -->
      <OrderStepsSection />

      <!-- Section 6: Kontak & Lokasi Workshop -->
      <ContactSection />

      <!-- Section 7: Footer -->
      <AppFooter />

      <!-- Floating WhatsApp Quick Button -->
      <FloatingWhatsApp />
    </div>
  </div>
</template>

<script setup>
import { onMounted, nextTick } from 'vue'
import Preloader from './components/Preloader.vue'
import AppHeader from './components/AppHeader.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import ProcessSection from './components/ProcessSection.vue'
import PortfolioSection from './components/PortfolioSection.vue'
import OrderStepsSection from './components/OrderStepsSection.vue'
import ContactSection from './components/ContactSection.vue'
import AppFooter from './components/AppFooter.vue'
import FloatingWhatsApp from './components/FloatingWhatsApp.vue'

onMounted(async () => {
  await nextTick()
  if (typeof window.initSitePlugins === 'function') {
    window.initSitePlugins()
  } else {
    const checkInit = setInterval(() => {
      if (typeof window.initSitePlugins === 'function') {
        window.initSitePlugins()
        clearInterval(checkInit)
      }
    }, 100)
    setTimeout(() => clearInterval(checkInit), 3000)
  }
})
</script>
