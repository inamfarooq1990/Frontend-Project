<script setup lang="ts">
import { ref } from 'vue'

const metrics = ref([
  { title: 'Revenue', value: '$12,426', change: '+12%', positive: true },
  { title: 'Users', value: '1,247', change: '+8%', positive: true },
  { title: 'Conversion', value: '3.2%', change: '-2%', positive: false },
  { title: 'Churn Rate', value: '2.1%', change: '-5%', positive: true }
])

const recentActivity = ref([
  { user: 'John Doe', action: 'Upgraded to Pro', time: '2 mins ago' },
  { user: 'Sarah Wilson', action: 'Signed up', time: '15 mins ago' },
  { user: 'Mike Johnson', action: 'Created project', time: '1 hour ago' },
  { user: 'Emily Davis', action: 'Invited team member', time: '2 hours ago' }
])
</script>

<template>
  <section id="dashboard" class="py-20 px-4 sm:px-6 lg:px-8 bg-gray-50">
    <div class="max-w-7xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-gray-900 mb-4">
          Powerful Dashboard & Analytics
        </h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Get real-time insights into your business performance with our comprehensive dashboard.
        </p>
      </div>
      
      <div class="bg-white rounded-2xl shadow-xl p-8">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
          <div v-for="metric in metrics" :key="metric.title" class="card p-6">
            <div class="flex items-center justify-between mb-2">
              <h3 class="text-sm font-medium text-gray-500">{{ metric.title }}</h3>
              <span :class="[
                'text-xs font-medium px-2 py-1 rounded-full',
                metric.positive ? 'text-green-700 bg-green-100' : 'text-red-700 bg-red-100'
              ]">
                {{ metric.change }}
              </span>
            </div>
            <p class="text-2xl font-bold text-gray-900">{{ metric.value }}</p>
          </div>
        </div>
        
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div class="card p-6">
            <h3 class="text-lg font-semibold text-gray-900 mb-4">Revenue Trend</h3>
            <div class="h-48 bg-gradient-to-r from-primary-50 to-secondary-50 rounded-lg flex items-end justify-center p-4">
              <div class="flex items-end space-x-2">
                <div v-for="i in 12" :key="i" 
                     class="bg-primary-500 rounded-t"
                     :style="{ height: `${Math.random() * 120 + 20}px`, width: '20px' }">
                </div>
              </div>
            </div>
          </div>
          
          <div class="card p-6">
            <h3 class="text-lg font-semibold text-gray-900 mb-4">Recent Activity</h3>
            <div class="space-y-4">
              <div v-for="activity in recentActivity" :key="activity.user" 
                   class="flex items-center space-x-3 p-3 hover:bg-gray-50 rounded-lg transition-colors">
                <div class="w-8 h-8 bg-primary-100 rounded-full flex items-center justify-center">
                  <span class="text-primary-600 text-sm font-medium">
                    {{ activity.user.charAt(0) }}
                  </span>
                </div>
                <div class="flex-1">
                  <p class="text-sm font-medium text-gray-900">{{ activity.user }}</p>
                  <p class="text-sm text-gray-500">{{ activity.action }}</p>
                </div>
                <span class="text-xs text-gray-400">{{ activity.time }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>