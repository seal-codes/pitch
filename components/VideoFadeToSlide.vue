<template>
  <div class="video-fade-container">
    <!-- Video Background -->
    <video
      ref="videoElement"
      :src="videoSrc"
      autoplay
      muted
      playsinline
      class="video-element"
      :class="{ 'video-fade-out': videoEnded }"
      @ended="handleVideoEnd"
    />
    
    <!-- Slide Content (revealed after video) -->
    <div 
      class="slide-content"
      :class="{ 'content-fade-in': videoEnded }"
    >
      <slot />
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const props = defineProps({
  videoSrc: {
    type: String,
    required: true
  }
})

const videoElement = ref(null)
const videoEnded = ref(false)

const handleVideoEnd = () => {
  videoEnded.value = true
}

onMounted(() => {
  // Ensure video plays from the beginning when slide is loaded
  if (videoElement.value) {
    videoElement.value.currentTime = 0
    videoElement.value.play()
  }
})
</script>

<style scoped>
.video-fade-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  z-index: 1;
}

.video-element {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  object-fit: cover;
  transition: opacity 1s ease-in-out;
  opacity: 1;
}

.video-fade-out {
  opacity: 0;
}

.slide-content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  transition: opacity 1s ease-in-out;
  opacity: 0;
}

.content-fade-in {
  opacity: 1;
}
</style>
