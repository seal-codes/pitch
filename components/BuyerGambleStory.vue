<template>
  <div class="h-full relative bg-gradient-to-br from-orange-50 to-orange-100 dark:from-orange-900/20 dark:to-orange-800/20">
    <div class="h-full flex flex-col justify-center px-16 py-12">
      <h1 class="text-5xl font-bold mb-6 text-orange-600 dark:text-orange-400 brand-accent">The Buyer's Gamble</h1>
      <h2 class="text-3xl mb-8 text-gray-800 dark:text-gray-200">Meet Alex</h2>
      
      <!-- Initial Uncertainty State -->
      <div v-show="!showSolution" class="transition-opacity duration-1000" :class="{ 'opacity-0': showSolution }">
        <p class="text-2xl leading-relaxed mb-8 text-gray-700 dark:text-gray-300">
          Alex wants to buy something online, but the marketplace is filled with doubt.
        </p>
        <p class="text-xl opacity-80 mb-12 text-gray-600 dark:text-gray-400">
          He's forced to gamble, unsure if a seller is legitimate or a scam.
        </p>
        <div class="mb-8">
          <img 
            src="/two-advertisements-with-and-without-seld-code.png" 
            alt="Marketplace comparison showing uncertainty" 
            class="rounded-lg shadow-lg max-w-2xl border border-gray-200"
          />
        </div>
        <div class="brand-card max-w-md bg-orange-100 dark:bg-orange-900/30 border-orange-200 dark:border-orange-700">
          <div class="flex items-center space-x-4">
            <lucide-alert-triangle class="text-orange-500 text-3xl" />
            <div>
              <p class="font-semibold text-orange-800 dark:text-orange-200">Trust Crisis</p>
              <p class="text-orange-600 dark:text-orange-300">Which seller can I trust?</p>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Solution State (After Next) -->
      <div v-show="showSolution" class="transition-opacity duration-1000" :class="{ 'opacity-100': showSolution, 'opacity-0': !showSolution }">
        <p class="text-2xl leading-relaxed mb-8 text-gray-700 dark:text-gray-300">
          With seal.codes, Alex can now transact with confidence.
        </p>
        <p class="text-xl opacity-80 mb-12 text-gray-600 dark:text-gray-400">
          The seal acts as a digital handshake, removing doubt and preventing fraud.
        </p>
        <div class="brand-card max-w-md bg-green-100 dark:bg-green-900/30 border-green-200 dark:border-green-700">
          <div class="text-center">
            <lucide-handshake class="text-6xl mb-6 mx-auto text-green-500" />
            <p class="text-xl font-semibold mb-2 text-green-800 dark:text-green-200">Digital Handshake</p>
            <p class="text-lg text-green-600 dark:text-green-300">Instant trust verification</p>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Alex's Portrait -->
    <div class="absolute bottom-8 right-8 transform" :class="showSolution ? 'rotate-1' : '-rotate-2'">
      <div class="polaroid transition-all duration-1000" :class="{ 'shadow-2xl border-green-300': showSolution }">
        <img 
          src="/alex-portrait.png" 
          alt="Alex portrait" 
          class="w-40 h-52 object-cover rounded transition-all duration-1000"
          :class="{ 'brightness-110 contrast-105': showSolution }"
        />
        <div class="text-center mt-2 text-gray-700 font-medium dark:text-gray-300 flex items-center justify-center gap-1 transition-all duration-500">
          Alex 
          <lucide-help-circle v-show="!showSolution" class="w-5 h-5 text-orange-500" />
          <lucide-thumbs-up v-show="showSolution" class="w-5 h-5 text-green-500" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const showSolution = ref(false)

// Listen for Slidev navigation events
function handleSlideChange() {
  // Show solution when navigating to this slide or beyond
  const currentSlide = window.location.hash || window.location.pathname
  const slideNumber = parseInt(currentSlide.match(/\/(\d+)/)?.[1] || '0')
  
  // Show solution if we're on slide 7 or later (after the buyer's gamble slide)
  if (slideNumber >= 7) {
    showSolution.value = true
  }
}

// Listen for Slidev's navigation events
function handleNavigation(event) {
  // Check if we're moving forward in the presentation
  if (event.detail && event.detail.no >= 6) { // Slide 6 is buyer's gamble
    setTimeout(() => {
      showSolution.value = true
    }, 500) // Small delay for better UX
  }
}

onMounted(() => {
  // Listen for Slidev's custom navigation events
  window.addEventListener('slidev:nav-click', handleNavigation)
  window.addEventListener('slidev:nav-next', handleNavigation)
  window.addEventListener('slidev:nav-go', handleNavigation)
  
  // Also listen for hash changes as fallback
  window.addEventListener('hashchange', handleSlideChange)
  
  // Check initial state
  handleSlideChange()
})

onUnmounted(() => {
  window.removeEventListener('slidev:nav-click', handleNavigation)
  window.removeEventListener('slidev:nav-next', handleNavigation)
  window.removeEventListener('slidev:nav-go', handleNavigation)
  window.removeEventListener('hashchange', handleSlideChange)
})
</script>

<style scoped>
/* Enhanced polaroid styling for the story */
.polaroid {
  background: white;
  padding: 0.75rem;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
  border: 2px solid rgba(249, 115, 22, 0.3);
  border-radius: 0.5rem;
  transform-origin: center;
  transition: all 0.5s ease;
}

.dark .polaroid {
  background: #f7f7f9;
  border: 2px solid rgba(249, 115, 22, 0.5);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
}

/* Smooth transitions for state changes */
.transition-opacity {
  transition: opacity 1s ease-in-out;
}

/* Enhanced image effects */
.brightness-110 {
  filter: brightness(110%) contrast(105%);
}

/* Brand accent line */
.brand-accent::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, #f97316 0%, #fb923c 100%);
  border-radius: 2px;
}
</style>