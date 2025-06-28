<template>
  <div class="h-full relative bg-gradient-to-br from-red-50 to-red-100 dark:from-red-900/20 dark:to-red-800/20">
    <div class="h-full flex flex-col justify-center px-16 py-12">
      <h1 class="text-5xl font-bold mb-6 text-red-600 dark:text-red-400">The Creator's Dilemma</h1>
      <h2 class="text-3xl mb-8 text-gray-800 dark:text-gray-200">Meet Sarah</h2>
      
      <!-- Working Story (Initial State) -->
      <div v-show="!isTheftRevealed" class="transition-opacity duration-1000" :class="{ 'opacity-0': isTheftRevealed }">
        <p class="text-2xl leading-relaxed mb-8 text-gray-700 dark:text-gray-300">
          Sarah works tirelessly on her art, pouring her heart and soul into every piece.
        </p>
        <p class="text-xl opacity-80 mb-12 text-gray-600 dark:text-gray-400">
          Her interaction with the world is through her beautiful creations.
        </p>
        <div class="mb-8">
          <img 
            src="/collage-assets-created-physical-world.png" 
            alt="Sarah working on her art" 
            class="rounded-lg shadow-lg max-w-2xl cursor-pointer hover:shadow-xl transition-shadow"
            @click="revealTheft"
          />
        </div>
        <p class="text-lg text-blue-600 dark:text-blue-400 font-medium cursor-pointer" @click="revealTheft">
          Click to see what happens next...
        </p>
      </div>
      
      <!-- Theft Story (After Click) -->
      <div v-show="isTheftRevealed" class="transition-opacity duration-1000" :class="{ 'opacity-100': isTheftRevealed, 'opacity-0': !isTheftRevealed }">
        <p class="text-2xl leading-relaxed mb-8 text-gray-700 dark:text-gray-300">
          But then her work is stolen and her ownership is erased.
        </p>
        <p class="text-xl opacity-80 mb-12 text-gray-600 dark:text-gray-400">
          The trust between her and her audience is broken. This happens millions of times every day.
        </p>
        <img 
          src="/social-media-unauthorized-copy.png" 
          alt="Stolen content example" 
          class="rounded-lg shadow-lg max-w-2xl"
        />
      </div>
    </div>
    
    <!-- Sarah's Portrait -->
    <div class="absolute bottom-8 right-8 transform rotate-3" :class="{ 'animate-shake': isTheftRevealed }">
      <div class="bg-white p-3 shadow-2xl rounded dark:bg-gray-800">
        <img 
          :src="portraitSrc" 
          alt="Sarah portrait" 
          class="w-40 h-52 object-cover rounded transition-all duration-1000"
          :class="{ 'filter grayscale contrast-125 brightness-75': isTheftRevealed }"
        />
        <div class="text-center mt-2 text-gray-700 font-medium dark:text-gray-300">
          Sarah {{ isTheftRevealed ? '😠' : '😊' }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const isTheftRevealed = ref(false)

const portraitSrc = computed(() => '/sarah-portrait.png')

function revealTheft() {
  isTheftRevealed.value = true
}
</script>

<style scoped>
@keyframes shake {
  0%, 100% { transform: rotate(3deg) translateX(0); }
  25% { transform: rotate(3deg) translateX(-2px); }
  75% { transform: rotate(3deg) translateX(2px); }
}

.animate-shake {
  animation: shake 0.5s ease-in-out;
}

.filter {
  filter: grayscale(100%) contrast(125%) brightness(75%);
}
</style>