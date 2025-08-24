<script setup lang="ts">
import { ref } from 'vue'

const isYearly = ref(false)

const plans = ref([
  {
    name: 'Starter',
    monthlyPrice: 9,
    yearlyPrice: 90,
    description: 'Perfect for small teams getting started',
    features: [
      'Up to 5 team members',
      '10GB storage',
      'Basic analytics',
      'Email support',
      'API access'
    ],
    popular: false
  },
  {
    name: 'Professional',
    monthlyPrice: 29,
    yearlyPrice: 290,
    description: 'Best for growing businesses',
    features: [
      'Up to 25 team members',
      '100GB storage',
      'Advanced analytics',
      'Priority support',
      'API access',
      'Custom integrations',
      'Advanced security'
    ],
    popular: true
  },
  {
    name: 'Enterprise',
    monthlyPrice: 99,
    yearlyPrice: 990,
    description: 'For large organizations',
    features: [
      'Unlimited team members',
      'Unlimited storage',
      'Custom analytics',
      'Dedicated support',
      'API access',
      'Custom integrations',
      'Enterprise security',
      'SLA guarantee',
      'Custom features'
    ],
    popular: false
  }
])

const toggleBilling = () => {
  isYearly.value = !isYearly.value
}
</script>

<template>
  <section id="pricing" class="py-20 px-4 sm:px-6 lg:px-8">
    <div class="max-w-7xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-gray-900 mb-4">
          Simple, Transparent Pricing
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto mb-8">
          Choose the plan that's right for your team. No hidden fees, cancel anytime.
        </p>
        
        <div class="flex items-center justify-center space-x-3">
          <span class="text-gray-700">Monthly</span>
          <button @click="toggleBilling" 
                  class="relative inline-flex h-6 w-11 flex-shrink-0 cursor-pointer rounded-full border-2 border-transparent transition-colors duration-200 ease-in-out focus:outline-none focus:ring-2 focus:ring-primary-600 focus:ring-offset-2"
                  :class="isYearly ? 'bg-primary-600' : 'bg-gray-200'">
            <span class="translate-x-0 pointer-events-none inline-block h-5 w-5 transform rounded-full bg-white shadow ring-0 transition duration-200 ease-in-out"
                  :class="isYearly ? 'translate-x-5' : 'translate-x-0'"></span>
          </button>
          <span class="text-gray-700">
            Yearly 
            <span class="text-primary-600 font-medium">(Save 17%)</span>
          </span>
        </div>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div v-for="plan in plans" :key="plan.name" 
             class="relative card p-8 hover:scale-105 transition-transform duration-200"
             :class="plan.popular ? 'ring-2 ring-primary-600' : ''">
          
          <div v-if="plan.popular" 
               class="absolute -top-3 left-1/2 transform -translate-x-1/2">
            <span class="bg-primary-600 text-white px-4 py-1 rounded-full text-sm font-medium">
              Most Popular
            </span>
          </div>
          
          <div class="text-center mb-8">
            <h3 class="text-2xl font-bold text-gray-900 mb-2">{{ plan.name }}</h3>
            <p class="text-gray-600 mb-4">{{ plan.description }}</p>
            <div class="flex items-baseline justify-center">
              <span class="text-4xl font-bold text-gray-900">
                ${{ isYearly ? plan.yearlyPrice / 12 : plan.monthlyPrice }}
              </span>
              <span class="text-gray-600 ml-1">/month</span>
            </div>
            <p v-if="isYearly" class="text-sm text-gray-500 mt-1">
              Billed annually (${{ plan.yearlyPrice }})
            </p>
          </div>
          
          <ul class="space-y-3 mb-8">
            <li v-for="feature in plan.features" :key="feature" class="flex items-center">
              <svg class="h-5 w-5 text-primary-600 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
              </svg>
              <span class="text-gray-700">{{ feature }}</span>
            </li>
          </ul>
          
          <button :class="plan.popular ? 'btn-primary w-full' : 'btn-secondary w-full'">
            Get Started
          </button>
        </div>
      </div>
    </div>
  </section>
</template>