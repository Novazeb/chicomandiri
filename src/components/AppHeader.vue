<template>
  <header class="section novi-background bg-cover page-header" id="home">
    <!-- RD Navbar-->
    <div class="rd-navbar-wrap">
      <nav 
        class="rd-navbar" 
        data-layout="rd-navbar-fixed" 
        data-sm-layout="rd-navbar-fixed" 
        data-md-layout="rd-navbar-fixed" 
        data-lg-layout="rd-navbar-fixed" 
        data-lg-device-layout="rd-navbar-fixed" 
        data-xl-layout="rd-navbar-fixed" 
        data-xl-device-layout="rd-navbar-fixed" 
        data-xxl-layout="rd-navbar-fixed" 
        data-xxl-device-layout="rd-navbar-fixed"
      >
        <div class="rd-navbar-main-outer">
          <div class="rd-navbar-main">
            <!-- RD Navbar Panel: Logo on left, Toggle on right (No overlapping button) -->
            <div class="rd-navbar-panel">
              <!-- RD Navbar Brand-->
              <div class="rd-navbar-brand">
                <a class="brand brand-logo-container" href="index.html">
                  <img src="/images/chico/logo.png" alt="Bengkel Las Chico Mandiri" class="brand-logo-img"/>
                  <div class="brand-text-wrapper">
                    <span class="brand-title">CHICO MANDIRI</span>
                    <span class="brand-subtitle">Metal Works &amp; Glass</span>
                  </div>
                </a>
              </div>

              <!-- RD Navbar Toggle-->
              <button class="rd-navbar-toggle" data-rd-navbar-toggle=".rd-navbar-nav-wrap"><span></span></button>
            </div>

            <!-- Slide-out Drawer Navigation -->
            <div class="rd-navbar-main-element">
              <div class="rd-navbar-nav-wrap">
                <!-- RD Navbar Nav-->
                <ul class="rd-navbar-nav">
                  <li class="rd-nav-item active"><a class="rd-nav-link" href="#home">Beranda</a></li>
                  <li class="rd-nav-item"><a class="rd-nav-link" href="#about">Keunggulan</a></li>
                  <li class="rd-nav-item"><a class="rd-nav-link" href="#services">Layanan</a></li>
                  <li class="rd-nav-item"><a class="rd-nav-link" href="#portfolio">Portofolio</a></li>
                  <li class="rd-nav-item"><a class="rd-nav-link" href="#contacts">Kontak</a></li>
                </ul>

                <div class="contacts-classic">
                  <div class="unit align-items-center">
                    <div class="unit-left"><span class="icon novi-icon fa-brands fa-whatsapp text-primary"></span></div>
                    <div class="unit-body">
                      <a class="contacts-classic-text text-primary" href="https://wa.me/6281376933039?text=Halo%20Bengkel%20Las%20Chico%20Mandiri,%20saya%20tertarik%20konsultasi%20pembuatan%20kanopi/pagar" target="_blank" rel="noopener noreferrer">0813-7693-3039</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </nav>
    </div>
  </header>
</template>

<script setup>
</script>

<style scoped>
</style>
