<template>
    <div>
      <button @click="isOpen = !isOpen" class="fixed top-0 right-0 m-4 z-10">
        <span class="bg-gray-600 block transition-all duration-300 ease-out h-0.5 w-6 rounded-sm" :class="isOpen ? 'rotate-45 translate-y-1' : ''"></span>
        <span class="bg-gray-600 block transition-all duration-300 ease-out h-0.5 w-6 rounded-sm my-0.5" :class="isOpen ? 'opacity-0' : ''"></span>
        <span class="bg-gray-600 block transition-all duration-300 ease-out h-0.5 w-6 rounded-sm" :class="isOpen ? '-rotate-45 -translate-y-1' : ''"></span>
      </button>
      <transition name="fade" appear>
        <div v-if="isOpen" class="fixed inset-0 bg-gray-200 flex flex-col justify-center items-center z-1">
          <div class="container w-11/12 mx-auto flex">
            <div class="w-1/2 flex">
              <div class="w-full flex items-center">
                <div class="w-1/2 flex flex-col">
                  <ul>
                    <li>
                      <a href="#" class="block font-semibold px-4 py-2 text-gray-700">Company</a>
                    </li>
                    <li>
                      <a href="#" class="block px-4 py-2 text-gray-700">About</a>
                    </li>
                    <li>
                      <a href="#" class="block px-4 py-2 text-gray-700">Team</a>
                    </li>
                    <li>
                      <a href="#" class="block px-4 py-2 text-gray-700">Blog</a>
                    </li>
                  </ul>
                </div>
                <div class="w-1/2 flex flex-col">
                  <ul>
                    <li>
                      <a href="#" class="block font-semibold px-4 py-2 text-gray-700">Follow</a>
                    </li>
                    <li>
                      <a href="#" class="block px-4 py-2 text-gray-700">Facebook</a>
                    </li>
                    <li>
                      <a href="#" class="block px-4 py-2 text-gray-700">Instagram</a>
                    </li>
                    <li>
                      <a href="#" class="block px-4 py-2 text-gray-700">LinkedIn</a>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
            <div class="w-1/2 flex">
              <ul>
                  <li class="p-8">
                    <a href="#" class="block text-5xl text-gray-700 font-semibold">HOME</a>
                  </li>
                  <li class="p-8">
                    <a href="#" class="block text-5xl text-gray-700 font-semibold">PROJECTS</a>
                  </li>
                  <li class="p-8">
                    <a href="#" class="block text-5xl text-gray-700 font-semibold">SERVICES</a>
                  </li>
                  <li class="p-8">
                    <a href="#" class="block text-5xl text-gray-700 font-semibold">CONTACT</a>
                  </li>
                </ul>
            </div>
          </div>
        </div>
      </transition>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const isOpen = ref(false)
  </script>
  
  <style scoped>
  .fade-enter-active, .fade-leave-active {
    transition: opacity 0.5s, transform 0.5s;
  }
  
  .fade-enter-from, .fade-leave-to {
    opacity: 0;
    transform: translateY(-100%);
  }
  </style>