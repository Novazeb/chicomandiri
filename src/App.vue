<template>
  <div>
    <!-- Preloader -->
    <Preloader />

    <div class="page">
      <!-- Header & Navigation -->
      <AppHeader />

      <!-- Section 1: Hero Section -->
      <HeroSection />

      <!-- Section 2: 3 Nilai Jual Utama (Trust Badges) & Estimasi -->
      <AboutSection />

      <!-- Section 3: Katalog Layanan (4 Kartu / Spesialisasi) -->
      <ProcessSection />

      <!-- Section 4: Galeri Proyek (Foto Asli Mereka) -->
      <PortfolioSection />

      <!-- Section 5: Kontak & Lokasi -->
      <ContactSection />

      <!-- Section 5: Footer -->
      <AppFooter />
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
import ContactSection from './components/ContactSection.vue'
import AppFooter from './components/AppFooter.vue'

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
