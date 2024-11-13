<template>
  <nav class="bg-white border-b border-gray-100 sticky top-0 z-30">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <!-- Logo Section -->
        <div class="flex items-center">
          <div class="flex-shrink-0 flex items-center space-x-3 group">
            <img
              src="https://www.zarla.com/website-builder/api/logo/e56226dae21393c9c4cfa35aee10c632c32324f5140177ac27a2b31eae80caf5"
              alt="Gidi Estate logo"
              class="h-10 w-10 transition-transform duration-300 group-hover:scale-110"
            />
            <span class="text-teal-600 text-xl font-bold tracking-tight group-hover:text-teal-700">
              Gidi Estate
            </span>
          </div>
        </div>

        <!-- Mobile Menu Button -->
        <div class="flex md:hidden items-center">
          <button
            @click="isMobileMenuOpen = !isMobileMenuOpen"
            class="text-gray-700 hover:text-teal-600 focus:outline-none"
          >
            <svg
              class="h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
            </svg>
          </button>
        </div>

        <!-- Desktop Navigation Links -->
        <div class="hidden md:flex items-center space-x-8">
          <router-link
            to="/"
            class="nav-link text-gray-700 hover:text-teal-600 font-medium transition-colors duration-200"
            active-class="text-teal-600 font-semibold"
          >
            HOME
          </router-link>
          <router-link
            to="/about"
            class="nav-link text-gray-700 hover:text-teal-600 font-medium transition-colors duration-200"
            active-class="text-teal-600 font-semibold"
          >
            ABOUT
          </router-link>

          <!-- Property Dropdown -->
          <div class="relative" @mouseleave="isPropertyDropdownOpen = false">
            <button
              @mouseenter="isPropertyDropdownOpen = true"
              class="flex items-center space-x-1 text-gray-700 hover:text-teal-600 font-medium transition-colors duration-200"
            >
              <span>PROPERTY</span>
              <svg
                class="w-4 h-4 transition-transform duration-200"
                :class="{ 'rotate-180': isPropertyDropdownOpen }"
              >
                <path
                  fill-rule="evenodd"
                  d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                />
              </svg>
            </button>

            <div
              v-show="isPropertyDropdownOpen"
              class="absolute left-0 mt-2 w-48 rounded-md shadow-lg py-1 bg-white ring-1 ring-black ring-opacity-5"
            >
              <router-link
                v-for="(item, index) in propertyLinks"
                :key="index"
                :to="item.to"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-teal-50 hover:text-teal-600 transition-colors duration-150"
              >
                {{ item.text }}
              </router-link>
            </div>
          </div>

          <router-link
            to="/contact"
            class="nav-link text-gray-700 hover:text-teal-600 font-medium transition-colors duration-200"
            active-class="text-teal-600 font-semibold"
          >
            CONTACT
          </router-link>
        </div>

        <!-- Add Property Button -->
        <div class="hidden md:flex items-center">
          <router-link
            to="/add-property"
            class="inline-flex items-center px-4 py-2 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-teal-600 hover:bg-teal-700"
          >
            Add Property
          </router-link>
        </div>
      </div>
    </div>

    <!-- Mobile Menu Links -->
    <div
      v-show="isMobileMenuOpen"
      class="md:hidden bg-white border-t border-gray-200 py-4 px-4 space-y-2"
    >
      <router-link
        to="/"
        class="block text-gray-700 hover:text-teal-600 font-medium transition-colors duration-200"
        @click="isMobileMenuOpen = false"
      >
        HOME
      </router-link>
      <router-link
        to="/about"
        class="block text-gray-700 hover:text-teal-600 font-medium transition-colors duration-200"
        @click="isMobileMenuOpen = false"
      >
        ABOUT
      </router-link>
      <router-link
        to="/contact"
        class="block text-gray-700 hover:text-teal-600 font-medium transition-colors duration-200"
        @click="isMobileMenuOpen = false"
      >
        CONTACT
      </router-link>
      <router-link
        to="/add-property"
        class="block text-gray-700 hover:text-teal-600 font-medium transition-colors duration-200"
        @click="isMobileMenuOpen = false"
      >
        Add Property
      </router-link>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)
const isPropertyDropdownOpen = ref(false)
const propertyLinks = [
  { to: '/property/list', text: 'List Property' },
  { to: '/property/sale', text: 'Property for Sale' },
]
</script>

<style scoped>
.nav-link {
  position: relative;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #0d9488;
  transition: width 0.2s ease-in-out;
}

.nav-link:hover::after,
.nav-link.router-link-active::after {
  width: 100%;
}
</style>
