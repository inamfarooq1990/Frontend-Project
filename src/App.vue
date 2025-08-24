<script setup lang="ts">
import Navigation from './components/Navigation.vue'
import Hero from './components/Hero.vue'
import Features from './components/Features.vue'
import Dashboard from './components/Dashboard.vue'
import Testimonials from './components/Testimonials.vue'
import Pricing from './components/Pricing.vue'
import CTA from './components/CTA.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="min-h-screen bg-gradient-to-br from-gray-50 via-white to-primary-50">
    <Navigation />
    <main>
      <Hero />
      <Features />
      <Dashboard />
      <Testimonials />
      <Pricing />
      <CTA />
    </main>
    <Footer />
  </div>
</template>