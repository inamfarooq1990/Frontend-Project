<script setup lang="ts">
import { ref } from 'vue'

const features = ref([
  {
    title: 'User Management',
    description: 'Complete user authentication, authorization, and profile management system.',
    icon: '👥',
    color: 'primary'
  },
  {
    title: 'Analytics Dashboard',
    description: 'Real-time analytics and insights to track your SaaS performance.',
    icon: '📊',
    color: 'secondary'
  },
  {
    title: 'Billing & Subscriptions',
    description: 'Integrated billing system with multiple payment options and subscription plans.',
    icon: '💳',
    color: 'primary'
  },
  {
    title: 'API Integration',
    description: 'RESTful APIs and webhooks for seamless third-party integrations.',
    icon: '🔗',
    color: 'secondary'
  },
  {
    title: 'Security First',
    description: 'Enterprise-grade security with encryption, compliance, and monitoring.',
    icon: '🔒',
    color: 'primary'
  },
  {
    title: '24/7 Support',
    description: 'Round-the-clock customer support and comprehensive documentation.',
    icon: '🚀',
    color: 'secondary'
  }
])
</script>

<template>
  <section id="features" class="py-20 px-4 sm:px-6 lg:px-8">
    <div class="max-w-7xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-gray-900 mb-4">
          Everything You Need to Scale
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Our comprehensive platform provides all the tools and features you need to build and grow your SaaS business.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="feature in features" :key="feature.title" 
             class="card p-8 hover:scale-105 transition-transform duration-200">
          <div class="text-4xl mb-4">{{ feature.icon }}</div>
          <h3 class="text-xl font-semibold text-gray-900 mb-3">{{ feature.title }}</h3>
          <p class="text-gray-600">{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>