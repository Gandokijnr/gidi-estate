<template>
  <div class="bg-white rounded-lg p-6 flex flex-col items-center container mx-auto py-12">
    <h2 class="text-2xl font-bold mb-4">Our Clients Say!</h2>
    <div class="relative w-7/12">
      <!-- Left Arrow -->
      <button
        @click="scrollLeft"
        class="absolute left-0 top-1/2 transform -translate-y-1/2 z-10 bg-teal-500 p-2 rounded-full shadow-lg"
      >
        <ChevronLeftIcon class="h-6 w-6 text-white" />
      </button>

      <!-- Scrollable Container -->
      <div
        ref="scrollContainer"
        class="flex gap-6 items-center overflow-x-auto scrollbar-hide w-full"
      >
        <div
          v-for="client in clients"
          :key="client.name"
          class="flex-shrink-0 w-80 bg-gray-100 rounded-lg p-4 flex items-center h-52"
        >
          <div class="flex-shrink-0 mr-4">
            <img :src="client.avatar" alt="Client Avatar" class="rounded-full w-16 h-16" />
          </div>
          <div>
            <p class="text-gray-600 italic">{{ client.quote }}</p>
            <div class="flex items-center mt-2">
              <p class="font-medium">{{ client.name }}</p>
              <div class="ml-2 flex items-center">
                <p class="mr-1 text-gray-600">{{ client.profession }}</p>
                <ChevronRightIcon class="h-4 w-4 text-gray-600" />
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Right Arrow -->
      <button
        @click="scrollRight"
        class="absolute right-0 top-1/2 transform -translate-y-1/2 z-10 bg-teal-500 p-2 rounded-full shadow-lg"
      >
        <ChevronRightIcon class="h-6 w-6 text-white" />
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { ChevronRightIcon, ChevronLeftIcon } from 'lucide-vue-next'

const scrollContainer = ref(null)

const scrollLeft = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollBy({ left: -200, behavior: 'smooth' })
  }
}

const scrollRight = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollBy({ left: 200, behavior: 'smooth' })
  }
}

const clients = [
  {
    avatar: 'src/assets/images/propertyagent/profilee.jpg',
    quote: '"Lorem ipsum dolor sit amet, consectetur adipiscing elit."',
    name: 'Client Name',
    profession: 'Profession',
  },
  {
    avatar: 'src/assets/images/propertyagent/profilee.jpg',
    quote: '"Tempor sunt labore dolor cillum amet ipsum dolor dolore."',
    name: 'Client Name',
    profession: 'Profession',
  },
  {
    avatar: 'src/assets/images/propertyagent/profilee.jpg',
    quote: '"Tempor sunt labore dolor cillum amet ipsum dolor dolore."',
    name: 'Client Name',
    profession: 'Profession',
  },
  {
    avatar: 'src/assets/images/propertyagent/profilee.jpg',
    quote: '"Tempor sunt labore dolor cillum amet ipsum dolor dolore."',
    name: 'Client Name',
    profession: 'Profession',
  },
  {
    avatar: 'src/assets/images/propertyagent/profilee.jpg',
    quote: '"Tempor sunt labore dolor cillum amet ipsum dolor dolore."',
    name: 'Client Name',
    profession: 'Profession',
  },
]
</script>

<style>
/* Hide default scrollbar for better UI */
.scrollbar-hide {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}

.scrollbar-hide::-webkit-scrollbar {
  display: none; /* Chrome, Safari, and Opera */
}
</style>
