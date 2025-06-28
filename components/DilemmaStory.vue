<template>
  <div class="h-full relative" :class="backgroundClass">
    <!-- Header Section -->
    <div class="absolute top-16 left-16 right-16 z-10">
      <h1 class="text-5xl font-bold mb-6" :class="titleColor">{{ title }}</h1>
    </div>

    <!-- Centered Image Section -->
    <div class="h-full flex items-center justify-center px-16 pt-32 pb-16">
      <!-- Initial State Image -->
      <div v-show="$clicks === 0" class="transition-all duration-1000 flex items-center justify-center h-full">
        <img 
          :src="initialImage" 
          :alt="initialImageAlt" 
          class="max-h-full max-w-full object-contain rounded-lg shadow-lg"
        />
      </div>
      
      <!-- Problem Revealed Image -->
      <div v-show="$clicks >= 1" class="transition-all duration-1000 flex items-center justify-center h-full">
        <img 
          :src="problemImage" 
          :alt="problemImageAlt" 
          class="max-h-full max-w-full object-contain rounded-lg shadow-lg"
        />
      </div>
    </div>
    
    <!-- Character Portrait -->
    <div class="absolute bottom-8 right-8 transform transition-all duration-1000" 
         :class="{ 'rotate-3': $clicks === 0, '-rotate-2 animate-shake': $clicks >= 1 }">
      <div class="bg-white p-3 shadow-2xl rounded">
        <img 
          :src="$clicks >= 1 ? frustratedPortrait : normalPortrait"
          :alt="`${characterName} portrait`" 
          class="w-60 h-60 object-cover rounded transition-all duration-1000"
        />
        <div class="text-center mt-2 text-gray-700 font-medium">
          {{ characterName }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  // Story content
  title: {
    type: String,
    required: true
  },
  // Images
  initialImage: {
    type: String,
    required: true
  },
  initialImageAlt: {
    type: String,
    required: true
  },
  problemImage: {
    type: String,
    required: true
  },
  problemImageAlt: {
    type: String,
    required: true
  },
  normalPortrait: {
    type: String,
    required: true
  },
  frustratedPortrait: {
    type: String,
    required: true
  },
  
  // Styling
  backgroundClass: {
    type: String,
    default: 'bg-gradient-to-br from-gray-50 to-gray-100'
  },
  titleColor: {
    type: String,
    default: 'text-red-600'
  },
  problemColor: {
    type: String,
    default: 'text-red-500'
  }
})
</script>

<style scoped>
@keyframes shake {
  0%, 100% { transform: rotate(-2deg) translateX(0); }
  25% { transform: rotate(-2deg) translateX(-2px); }
  75% { transform: rotate(-2deg) translateX(2px); }
}

.animate-shake {
  animation: shake 0.5s ease-in-out;
}
</style>
