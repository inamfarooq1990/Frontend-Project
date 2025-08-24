<script setup lang="ts">
import { ref } from 'vue'

const testimonials = ref([
  {
    name: 'Sarah Johnson',
    role: 'CEO, TechStart',
    content: 'SaasFlow transformed how we manage our SaaS business. The analytics dashboard is incredibly insightful.',
    avatar: 'https://images.pexels.com/photos/774909/pexels-photo-774909.jpeg?auto=compress&cs=tinysrgb&w=150&h=150&fit=crop',
    rating: 5
  },
  {
    name: 'Michael Chen',
    role: 'CTO, DataFlow',
    content: 'The API integration capabilities are outstanding. We were able to connect all our tools seamlessly.',
    avatar: 'https://images.pexels.com/photos/220453/pexels-photo-220453.jpeg?auto=compress&cs=tinysrgb&w=150&h=150&fit=crop',
    rating: 5
  },
  {
    name: 'Emily Rodriguez',
    role: 'Founder, GrowthLabs',
    content: 'Best decision we made for our startup. The billing system works flawlessly and saves us hours.',
    avatar: 'https://images.pexels.com/photos/415829/pexels-photo-415829.jpeg?auto=compress&cs=tinysrgb&w=150&h=150&fit=crop',
    rating: 5
  }
])
</script>

<template>
  <section class="py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-primary-50 to-secondary-50">
    <div class="max-w-7xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-gray-900 mb-4">
          Trusted by Growing Teams
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          See what our customers are saying about their experience with SaasFlow.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div v-for="testimonial in testimonials" :key="testimonial.name" 
             class="card p-8 hover:scale-105 transition-transform duration-200">
          <div class="flex items-center mb-4">
            <div v-for="i in testimonial.rating" :key="i" class="text-yellow-400">
              <svg class="h-5 w-5" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
              </svg>
            </div>
          </div>
          <p class="text-gray-700 mb-6 italic">
            "{{ testimonial.content }}"
          </p>
          <div class="flex items-center">
            <img :src="testimonial.avatar" 
                 :alt="testimonial.name"
                 class="w-12 h-12 rounded-full mr-4 object-cover">
            <div>
              <h4 class="font-semibold text-gray-900">{{ testimonial.name }}</h4>
              <p class="text-gray-600 text-sm">{{ testimonial.role }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>