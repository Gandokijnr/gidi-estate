<template>
  <div class="p-12">
    <div
      class="bg-white rounded-lg shadow-lg container mx-auto grid place-items-evenly text-center"
    >
      <h2 class="text-2xl font-bold mb-4 px-6 pt-6 text-center">Property Agents</h2>
      <p class="text-gray-500 text-sm mb-4 px-6">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec vel tristique neque.
      </p>
      <p class="text-gray-500 text-sm mb-4 px-6">
        Donec in ligula vitae felis eleifend scelerisque.
      </p>
      <div class="grid grid-cols-2 sm:grid-cols-4 gap-6 px-6 pb-20 py-20">
        <div v-for="agent in agents" :key="agent.id" class="flex flex-col items-center">
          <img :src="agent.image" alt="Agent" class="rounded-full w-24 h-24 mb-2" />
          <h3 class="text-lg font-medium">{{ agent.name }}</h3>
          <p class="text-gray-500">{{ agent.designation }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const agents = ref([
  {
    id: 1,
    name: 'Gandoki',
    designation: 'Web Developer',
    image: '/propertyagent/profilee.jpg',
  },
  {
    id: 2,
    name: 'Gandoki',
    designation: 'Web Developer',
    image: '/propertyagent/profilee.jpg',
  },
  {
    id: 3,
    name: 'Gandoki',
    designation: 'Web Developer',
    image: '/propertyagent/profilee.jpg',
  },
  {
    id: 4,
    name: 'Gandoki',
    designation: 'Web Developer',
    image: '/propertyagent/profilee.jpg',
  },
])
</script>
