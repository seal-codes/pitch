<template>
  <div class="video-fade-container">
    <!-- Video Background -->
    <video v-if="!videoRemoved" ref="videoElement" :src="videoSrc" autoplay muted playsinline class="video-element"
      :class="{ 'video-fade-out': videoEnded }" @ended="handleVideoEnd" />
    <!-- Slide Content (revealed after video) -->
    <div v-if="videoRemoved" class="slide-content" :class="{ 'content-fade-in': videoEnded }">
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
const videoRemoved = ref(false)

const handleVideoEnd = () => {
  videoEnded.value = true
  setTimeout(() => {
    videoRemoved.value = true
  }, 1000)
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
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: 1;
}

.video-element {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: opacity 1s ease-in-out;
  opacity: 1;
}

.video-fade-out {
  opacity: 0;
}

.slide-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
  text-align: center;
  transition: opacity 1s ease-in-out;
  opacity: 0;
}

.content-fade-in {
  opacity: 1;
}
</style>
