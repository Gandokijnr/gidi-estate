<!-- PropertyCard.vue -->
<template>
  <div class="bg-white shadow-md rounded-lg overflow-hidden p-8">
    <img :src="property.imageUrl" :alt="property.address" class="w-full h-56 object-cover" />
    <div class="p-4">
      <div class="flex items-center justify-between mb-2">
        <span class="bg-green-500 text-white px-3 py-1 rounded text-sm">{{ property.status }}</span>
        <span class="text-gray-500 text-sm">{{ property.type }}</span>
      </div>
      <h3 class="text-lg font-bold">{{ property.address }}</h3>
      <p class="text-gray-600 text-sm">{{ property.location }}</p>
      <div class="flex items-center justify-between mt-4">
        <p class="text-gray-700 font-bold text-2xl">{{ property.price }}</p>
        <div class="flex items-center space-x-1">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5 text-gray-500"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0"
            />
          </svg>
          <span class="text-gray-500 text-sm">{{ property.bedrooms }} Bed</span>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5 text-gray-500"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857M16 17L20 3"
            />
          </svg>
          <span class="text-gray-500 text-sm">{{ property.bathrooms }} Bathrooms</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'

defineProps({
  property: {
    type: Object,
    required: true,
  },
})
</script>
