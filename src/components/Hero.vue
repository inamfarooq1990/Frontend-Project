<script setup lang="ts">
import { ref } from 'vue'

const stats = ref([
  { value: '10k+', label: 'Active Users' },
  { value: '99.9%', label: 'Uptime' },
  { value: '50+', label: 'Integrations' },
  { value: '24/7', label: 'Support' }
])
</script>

<template>
  <section class="pt-20 pb-16 px-4 sm:px-6 lg:px-8">
    <div class="max-w-7xl mx-auto">
      <div class="text-center">
        <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-gray-900 mb-6 animate-fade-in">
          Build Your SaaS
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary-600 to-secondary-600">
            Faster Than Ever
          </span>
        </h1>
        <p class="text-xl text-gray-600 mb-8 max-w-3xl mx-auto animate-slide-up">
          SaasFlow provides everything you need to launch, manage, and scale your SaaS application. 
          From user management to billing, we've got you covered.
        </p>
        <div class="flex flex-col sm:flex-row justify-center items-center space-y-4 sm:space-y-0 sm:space-x-4 mb-16">
          <button class="btn-primary text-lg px-8 py-4">Start Free Trial</button>
          <button class="btn-secondary text-lg px-8 py-4">View Demo</button>
        </div>
      </div>
      
      <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mt-16">
        <div v-for="stat in stats" :key="stat.label" class="text-center">
          <div class="text-3xl font-bold text-primary-600 mb-2">{{ stat.value }}</div>
          <div class="text-gray-600">{{ stat.label }}</div>
        </div>
      </div>
    </div>
  </section>
</template>