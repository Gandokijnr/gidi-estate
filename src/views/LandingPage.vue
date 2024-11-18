<script setup>
import { ref } from 'vue'
import { RouterLink } from 'vue-router'
import { ChevronLeft, ChevronRight } from 'lucide-vue-next'
import PropertyTypesGrid from '@/components/PropertyTypesGrid.vue'
import PropertySection from '@/components/PropertySection.vue'
import PropertyCard from '@/components/PropertyListing.vue'
import ContactSection from '@/components/ContactSection.vue'
import PropertyAgent from '@/components/PropertyAgent.vue'
import ClientTestimonials from '@/components/ClientTestimonials.vue'

const properties = ref([
  {
    id: 1,
    status: 'Villa',
    bedrooms: 4,
    bathrooms: 6,
    location: '123 Street, New York, USA',
    type: 'Apartment',
    imageUrl: '/landingpage/fourth.jpg',
    price: '$11,345',
  },
  {
    id: 2,
    status: 'Office',
    bedrooms: 4,
    bathrooms: 6,
    location: '123 Street, New York, USA',
    type: 'Rent',
    imageUrl: '/landingpage/first.jpg',
    price: '$245 / Month',
  },
  {
    id: 3,
    status: 'Apartments',
    bedrooms: 4,
    bathrooms: 6,
    location: '123 Street, New York, USA',
    type: 'Apartment',
    imageUrl: '/landingpage/fourth.jpg',
    price: '$12,345',
  },
  {
    id: 4,
    status: 'Apartments',
    bedrooms: 4,
    bathrooms: 6,
    location: '123 Street, New York, USA',
    type: 'Apartment',
    imageUrl: '/landingpage/third.jpg',
    price: '$20,135',
  },
  {
    id: 5,
    status: 'Apartments',
    bedrooms: 4,
    bathrooms: 6,
    location: '123 Street, New York, USA',
    type: 'Apartment',
    imageUrl: '/landingpage/second.jpg',
    price: '$10,215',
  },
  {
    id: 6,
    status: 'Rents',
    bedrooms: 4,
    bathrooms: 6,
    location: '123 Street, New York, USA',
    type: 'Apartment',
    imageUrl: '/landingpage/first.jpg',
    price: '$1,345 / Month',
  },
])

const images = ref([
  '/landingpage/first.jpg',
  '/landingpage/second.jpg',
  '/landingpage/third.jpg',
  '/landingpage/fourth.jpg',
])

const currentImageIndex = ref(0)

const nextImage = () => {
  currentImageIndex.value = (currentImageIndex.value + 1) % images.value.length
}

const prevImage = () => {
  currentImageIndex.value =
    currentImageIndex.value === 0 ? images.value.length - 1 : currentImageIndex.value - 1
}
</script>

<template>
  <div class="min-h-screen bg-white">
    <!-- Hero Section -->
    <div class="relative w-full max-w-7xl mx-auto">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 p-4 lg:p-8">
        <!-- Left Content -->
        <div class="flex flex-col justify-center space-y-6">
          <h1 class="text-4xl lg:text-5xl font-bold">
            <span class="text-navy-900">Find A </span>
            <span class="text-teal-600">Perfect Home</span>
            <span class="text-navy-900"> To Live With Gidi Estate</span>
          </h1>

          <p class="text-gray-600">
            Vero elitr justo clita lorem. Ipsum dolor sit sed stetstat diam no. Kasd rebum ipsum et
            diam justo clita et kasd rebum sea elitr.
          </p>

          <button
            class="bg-teal-600 text-white px-8 py-3 rounded-md w-fit hover:bg-emerald-600 transition-colors"
          >
            Get Started
          </button>
        </div>

        <!-- Right Image Carousel -->
        <div class="relative overflow-hidden rounded-lg">
          <div class="relative h-[400px] w-full">
            <img
              :src="images[currentImageIndex]"
              class="absolute w-full h-full object-cover transition-opacity duration-500"
              alt="Home preview"
            />
          </div>

          <!-- Navigation Buttons -->
          <button
            @click="prevImage"
            class="absolute left-4 top-1/2 -translate-y-1/2 bg-teal-600 p-2 rounded-full hover:bg-emerald-600 transition-colors"
          >
            <ChevronLeft class="w-6 h-6 text-white" />
          </button>

          <button
            @click="nextImage"
            class="absolute right-4 top-1/2 -translate-y-1/2 bg-teal-600 p-2 rounded-full hover:bg-emerald-600 transition-colors"
          >
            <ChevronRight class="w-6 h-6 text-white" />
          </button>
        </div>
      </div>

      <!-- Search Bar -->
      <div class="w-full bg-teal-600 p-4 mt-8 rounded-lg">
        <div class="flex flex-col md:flex-row gap-4">
          <input type="text" placeholder="Search Keyword" class="flex-1 p-3 rounded-md" />

          <select class="flex-1 p-3 rounded-md">
            <option value="">Property Type</option>
          </select>

          <select class="flex-1 p-3 rounded-md">
            <option value="">Location</option>
          </select>

          <button
            class="bg-navy-900 text-white px-8 py-3 rounded-md hover:bg-navy-800 transition-colors bg-emerald-800"
          >
            Search
          </button>
        </div>
      </div>
    </div>
    <!-- Property Type Grid -->
    <PropertyTypesGrid />

    <!-- Property section components -->
    <PropertySection />

    <!-- property listing components -->
    <div class="container mx-auto py-8 grid place-items-center">
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6 mb-12">
        <PropertyCard v-for="property in properties" :key="property.id" :property="property" />
      </div>
      <RouterLink :to="{ name: 'home' }" class="bg-teal-600 p-4 text-white rounded capitalize"
        >View more properties</RouterLink
      >
    </div>

    <!-- contact section components -->
    <ContactSection />

    <!-- property agent components -->
    <PropertyAgent />

    <!-- client testimonial components -->
    <ClientTestimonials />
  </div>
</template>

<style scoped>
.text-navy-900 {
  color: #1a365d;
}
</style>
