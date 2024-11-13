<template>
  <div class="max-w-4xl mx-auto px-4 py-24">
    <!-- Header -->
    <h1 class="text-3xl font-bold text-center text-gray-800 mb-2">Property Types</h1>
    <p class="text-center text-gray-600 mb-8">
      Eirmod sed ipsum dolor sit rebum labore magna erat. Tempor ut dolore lorem kasd vero ipsum sit
      eirmod sit. Ipsum diam justo sed rebum vero dolor duo.
    </p>

    <!-- Grid -->
    <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
      <div
        v-for="property in propertyTypes"
        :key="property.type"
        class="p-6 border rounded-lg group hover:bg-emerald-500 transition-all duration-300"
      >
        <div class="flex flex-col items-center">
          <!-- Icon -->
          <div class="w-16 h-16 rounded-full border-2 border-dashed p-3 mb-4 bg-white">
            <img :src="property.icon" :alt="property.type" class="w-full h-full" />
          </div>
          <!-- Property Type -->
          <h3 class="font-semibold mb-2 group-hover:text-white">
            {{ property.type }}
          </h3>
          <!-- Property Count -->
          <p
            :class="[
              'text-sm',
              property.type === 'Garage' ? 'text-white' : 'text-emerald-500',
              'group-hover:text-white',
            ]"
          >
            {{ property.count }} Properties
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const propertyTypes = [
  {
    type: 'Apartment',
    count: 123,
    icon: 'src/assets/icons/icon-apartment.png',
  },
  {
    type: 'Villa',
    count: 123,
    icon: 'src/assets/icons/icon-villa.png',
  },
  {
    type: 'Home',
    count: 123,
    icon: 'src/assets/icons/icon-house.png',
  },
  {
    type: 'Office',
    count: 123,
    icon: 'src/assets/icons/icon-luxury.png',
  },
  {
    type: 'Building',
    count: 123,
    icon: 'src/assets/icons/icon-building.png',
  },
  {
    type: 'Townhouse',
    count: 123,
    icon: 'src/assets/icons/icon-neighborhood.png',
  },
  {
    type: 'Shop',
    count: 123,
    icon: 'src/assets/icons/icon-condominium.png',
  },
  {
    type: 'Garage',
    count: 123,
    icon: 'src/assets/icons/icon-housing.png',
  },
]
</script>
