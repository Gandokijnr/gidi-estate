<template>
  <footer class="bg-teal-900 text-gray-400 py-12">
    <div class="container mx-auto px-4 grid grid-cols-1 md:grid-cols-4 gap-8">
      <div>
        <h3 class="text-white font-bold mb-4">Get In Touch</h3>
        <p>123 Street, New York, USA</p>
        <p>+012 345 67890</p>
        <p>mail@domain.com</p>
        <div class="flex space-x-4 mt-4">
          <RouterLink to="#" class="text-gray-400 hover:text-white">
            <i class="fab fa-twitter"></i>
          </RouterLink>
          <RouterLink to="#" class="text-gray-400 hover:text-white">
            <i class="fab fa-facebook-f"></i>
          </RouterLink>
          <RouterLink to="#" class="text-gray-400 hover:text-white">
            <i class="fab fa-youtube"></i>
          </RouterLink>
          <RouterLink to="#" class="text-gray-400 hover:text-white">
            <i class="fab fa-linkedin-in"></i>
          </RouterLink>
        </div>
      </div>

      <div>
        <h3 class="text-white font-bold mb-4">Quick Links</h3>
        <ul class="space-y-2">
          <li><RouterLink to="/about" class="hover:text-white">About Us</RouterLink></li>
          <li><RouterLink to="/contact" class="hover:text-white">Contact Us</RouterLink></li>
          <li><RouterLink to="/services" class="hover:text-white">Our Services</RouterLink></li>
          <li>
            <RouterLink to="/privacy-policy" class="hover:text-white">Privacy Policy</RouterLink>
          </li>
          <li><RouterLink to="/terms" class="hover:text-white">Terms & Conditions</RouterLink></li>
        </ul>
      </div>

      <div>
        <h3 class="text-white font-bold mb-4">Photo Gallery</h3>
        <div class="grid grid-cols-3 gap-2">
          <img
            v-for="(image, index) in galleryImages"
            :key="index"
            :src="image"
            alt="Gallery Image"
            class="w-full h-auto"
          />
        </div>
      </div>

      <div>
        <h3 class="text-white font-bold mb-4">Newsletter</h3>
        <p>Dolor amet sit justo amet elit clita ipsum elit est.</p>
        <div class="mt-4">
          <input
            type="email"
            placeholder="Your email"
            class="bg-gray-800 text-gray-400 px-4 py-2 rounded-l-md"
          />
          <button class="bg-teal-500 text-white px-4 py-2 rounded-r-md">SignUp</button>
        </div>
      </div>
    </div>
    <div class="text-center mt-8">
      <p>
        &copy; Gidi Estate, All Rights Reserved. Designed By
        <a
          href="https://wa.me/yourphonenumber"
          target="_blank"
          class="text-teal-500 hover:text-teal-400"
        >
          Gandoki
        </a>
      </p>
    </div>
  </footer>
</template>

<script setup>
import { RouterLink } from 'vue-router'

const galleryImages = [
  'src/assets/images/landingpage/second.jpg',
  'src/assets/images/landingpage/second.jpg',
  'src/assets/images/landingpage/second.jpg',
  'src/assets/images/landingpage/second.jpg',
  'src/assets/images/landingpage/second.jpg',
  'src/assets/images/landingpage/second.jpg',
]
</script>
