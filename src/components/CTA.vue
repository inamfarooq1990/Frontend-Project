<script setup lang="ts">
import { ref } from 'vue'

const email = ref('')

const handleSignup = () => {
  if (email.value) {
    console.log('Signup with email:', email.value)
    // Handle signup logic here
    email.value = ''
  }
}
</script>

<template>
  <section class="py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-r from-primary-600 to-secondary-600">
    <div class="max-w-4xl mx-auto text-center">
      <h2 class="text-3xl sm:text-4xl font-bold text-white mb-6">
        Ready to Transform Your SaaS Business?
      </h2>
      <p class="text-xl text-primary-100 mb-8 max-w-2xl mx-auto">
        Join thousands of companies that trust SaasFlow to power their growth. 
        Start your free trial today and see the difference.
      </p>
      
      <div class="flex flex-col sm:flex-row justify-center items-center space-y-4 sm:space-y-0 sm:space-x-4 mb-8">
        <input v-model="email"
               type="email" 
               placeholder="Enter your work email"
               class="w-full sm:w-80 px-6 py-4 rounded-lg text-gray-900 placeholder-gray-500 focus:outline-none focus:ring-4 focus:ring-white/30">
        <button @click="handleSignup"
                class="w-full sm:w-auto bg-white hover:bg-gray-100 text-primary-600 font-semibold px-8 py-4 rounded-lg transition-all duration-200 shadow-lg hover:shadow-xl">
          Start Free Trial
        </button>
      </div>
      
      <div class="flex flex-col sm:flex-row justify-center items-center space-y-2 sm:space-y-0 sm:space-x-8 text-primary-100">
        <div class="flex items-center">
          <svg class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
          </svg>
          <span>14-day free trial</span>
        </div>
        <div class="flex items-center">
          <svg class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
          </svg>
          <span>No credit card required</span>
        </div>
        <div class="flex items-center">
          <svg class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
          </svg>
          <span>Cancel anytime</span>
        </div>
      </div>
    </div>
  </section>
</template>