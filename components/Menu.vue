<template>
    <div>
      <button @click="isOpen = !isOpen" class="fixed top-0 right-0 m-4 z-10">
        <span class="bg-gray-600 block transition-all duration-300 ease-out h-0.5 w-6 rounded-sm" :class="isOpen ? 'rotate-45 translate-y-1' : ''"></span>
        <span class="bg-gray-600 block transition-all duration-300 ease-out h-0.5 w-6 rounded-sm my-0.5" :class="isOpen ? 'opacity-0' : ''"></span>
        <span class="bg-gray-600 block transition-all duration-300 ease-out h-0.5 w-6 rounded-sm" :class="isOpen ? '-rotate-45 -translate-y-1' : ''"></span>
      </button>
      <transition name="fade" appear>
        <ul v-if="isOpen" class="fixed inset-0 bg-gray-500 flex flex-col justify-center items-center z-1">
          <li>
            <a href="#" class="block px-4 py-2 text-gray-700 hover:bg-gray-200">Accueil</a>
          </li>
          <li>
            <a href="#" class="block px-4 py-2 text-gray-700 hover:bg-gray-200">À propos</a>
          </li>
          <li>
            <a href="#" class="block px-4 py-2 text-gray-700 hover:bg-gray-200">Contact</a>
          </li>
        </ul>
      </transition>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const isOpen = ref(false)
  </script>
  
  <style scoped>
  button {
    @apply bg-transparent border-none p-0 w-8 h-8;
  }
  
  .fade-enter-active, .fade-leave-active {
    transition: opacity 0.5s, transform 0.5s;
  }
  
  .fade-enter-from, .fade-leave-to {
    opacity: 0;
    transform: translateY(-100%);
  }
  </style>