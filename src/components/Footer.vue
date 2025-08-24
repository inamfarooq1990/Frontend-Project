<script setup lang="ts">
import { ref } from 'vue'

const footerLinks = ref({
  product: [
    { name: 'Features', href: '#features' },
    { name: 'Dashboard', href: '#dashboard' },
    { name: 'Pricing', href: '#pricing' },
    { name: 'API Docs', href: '#' },
    { name: 'Integrations', href: '#' }
  ],
  company: [
    { name: 'About Us', href: '#' },
    { name: 'Blog', href: '#' },
    { name: 'Careers', href: '#' },
    { name: 'Press', href: '#' },
    { name: 'Contact', href: '#' }
  ],
  support: [
    { name: 'Help Center', href: '#' },
    { name: 'Community', href: '#' },
    { name: 'Status', href: '#' },
    { name: 'Security', href: '#' },
    { name: 'Privacy', href: '#' }
  ],
  legal: [
    { name: 'Privacy Policy', href: '#' },
    { name: 'Terms of Service', href: '#' },
    { name: 'Cookie Policy', href: '#' },
    { name: 'GDPR', href: '#' }
  ]
})

const socialLinks = ref([
  { name: 'Twitter', href: '#', icon: 'M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z' },
  { name: 'GitHub', href: '#', icon: 'M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22' },
  { name: 'LinkedIn', href: '#', icon: 'M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z' }
])
</script>

<template>
  <footer class="bg-gray-900 text-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-8">
        <!-- Company Info -->
        <div class="lg:col-span-1">
          <h2 class="text-2xl font-bold text-white mb-4">SaasFlow</h2>
          <p class="text-gray-400 mb-6">
            Empowering businesses to build, launch, and scale their SaaS applications with confidence.
          </p>
          <div class="flex space-x-4">
            <a v-for="social in socialLinks" :key="social.name" 
               :href="social.href"
               class="text-gray-400 hover:text-white transition-colors">
              <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" :d="social.icon" />
              </svg>
            </a>
          </div>
        </div>
        
        <!-- Product Links -->
        <div>
          <h3 class="text-lg font-semibold text-white mb-4">Product</h3>
          <ul class="space-y-3">
            <li v-for="link in footerLinks.product" :key="link.name">
              <a :href="link.href" class="text-gray-400 hover:text-white transition-colors">
                {{ link.name }}
              </a>
            </li>
          </ul>
        </div>
        
        <!-- Company Links -->
        <div>
          <h3 class="text-lg font-semibold text-white mb-4">Company</h3>
          <ul class="space-y-3">
            <li v-for="link in footerLinks.company" :key="link.name">
              <a :href="link.href" class="text-gray-400 hover:text-white transition-colors">
                {{ link.name }}
              </a>
            </li>
          </ul>
        </div>
        
        <!-- Support Links -->
        <div>
          <h3 class="text-lg font-semibold text-white mb-4">Support</h3>
          <ul class="space-y-3">
            <li v-for="link in footerLinks.support" :key="link.name">
              <a :href="link.href" class="text-gray-400 hover:text-white transition-colors">
                {{ link.name }}
              </a>
            </li>
          </ul>
        </div>
        
        <!-- Legal Links -->
        <div>
          <h3 class="text-lg font-semibold text-white mb-4">Legal</h3>
          <ul class="space-y-3">
            <li v-for="link in footerLinks.legal" :key="link.name">
              <a :href="link.href" class="text-gray-400 hover:text-white transition-colors">
                {{ link.name }}
              </a>
            </li>
          </ul>
        </div>
      </div>
      
      <!-- Newsletter Signup -->
      <div class="border-t border-gray-800 mt-12 pt-8">
        <div class="flex flex-col md:flex-row items-center justify-between">
          <div class="mb-4 md:mb-0">
            <h3 class="text-lg font-semibold text-white mb-2">Stay Updated</h3>
            <p class="text-gray-400">Get the latest news and updates from SaasFlow.</p>
          </div>
          <div class="flex w-full md:w-auto">
            <input type="email" 
                   placeholder="Enter your email"
                   class="flex-1 md:w-80 px-4 py-3 rounded-l-lg bg-gray-800 border border-gray-700 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-primary-600 focus:border-transparent">
            <button class="bg-primary-600 hover:bg-primary-700 text-white px-6 py-3 rounded-r-lg font-medium transition-colors">
              Subscribe
            </button>
          </div>
        </div>
      </div>
      
      <!-- Copyright -->
      <div class="border-t border-gray-800 mt-8 pt-8 text-center">
        <p class="text-gray-400">
          © 2025 SaasFlow. All rights reserved. Built with Vue 3 and Tailwind CSS.
        </p>
      </div>
    </div>
  </footer>
</template>