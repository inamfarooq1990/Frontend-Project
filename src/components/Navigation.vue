<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <nav class="fixed w-full z-50 bg-white/95 backdrop-blur-sm border-b border-gray-200">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <div class="flex items-center">
          <div class="flex-shrink-0">
            <h1 class="text-2xl font-bold text-primary-600">SaasFlow</h1>
          </div>
        </div>
        
        <div class="hidden md:block">
          <div class="ml-10 flex items-baseline space-x-8">
            <a href="#features" class="text-gray-700 hover:text-primary-600 px-3 py-2 text-sm font-medium transition-colors">Features</a>
            <a href="#dashboard" class="text-gray-700 hover:text-primary-600 px-3 py-2 text-sm font-medium transition-colors">Dashboard</a>
            <a href="#pricing" class="text-gray-700 hover:text-primary-600 px-3 py-2 text-sm font-medium transition-colors">Pricing</a>
            <a href="#" class="text-gray-700 hover:text-primary-600 px-3 py-2 text-sm font-medium transition-colors">Contact</a>
          </div>
        </div>
        
        <div class="hidden md:block">
          <div class="ml-4 flex items-center md:ml-6 space-x-4">
            <button class="text-gray-700 hover:text-primary-600 px-3 py-2 text-sm font-medium transition-colors">Sign In</button>
            <button class="btn-primary">Get Started</button>
          </div>
        </div>
        
        <div class="md:hidden">
          <button @click="toggleMenu" class="text-gray-700 hover:text-primary-600 p-2">
            <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path v-if="!isMenuOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
              <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>
    </div>
    
    <div v-if="isMenuOpen" class="md:hidden bg-white border-t border-gray-200">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
        <a href="#features" class="text-gray-700 hover:text-primary-600 block px-3 py-2 text-base font-medium">Features</a>
        <a href="#dashboard" class="text-gray-700 hover:text-primary-600 block px-3 py-2 text-base font-medium">Dashboard</a>
        <a href="#pricing" class="text-gray-700 hover:text-primary-600 block px-3 py-2 text-base font-medium">Pricing</a>
        <a href="#" class="text-gray-700 hover:text-primary-600 block px-3 py-2 text-base font-medium">Contact</a>
        <div class="pt-4 pb-3 border-t border-gray-200">
          <button class="w-full text-left text-gray-700 hover:text-primary-600 block px-3 py-2 text-base font-medium">Sign In</button>
          <button class="btn-primary w-full mt-2">Get Started</button>
        </div>
      </div>
    </div>
  </nav>
</template>