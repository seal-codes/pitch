<template>
  <div class="video-container">
    <video
      ref="videoRef"
      autoplay
      muted
      playsinline
      class="video-element"
      :poster="poster"
    >
      <source :src="src" type="video/mp4" />
      Your browser does not support the video tag.
    </video>

    <div class="content-overlay">
      <slot />
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const props = defineProps({
  src: {
    type: String,
    required: true,
  },
  poster: {
    type: String,
    default: "",
  },
});

const videoRef = ref(null);
let observer = null;

const restartVideo = () => {
  if (videoRef.value) {
    videoRef.value.currentTime = 0;
    videoRef.value.play().catch(() => {
      // Handle autoplay restrictions gracefully
    });
  }
};

onMounted(() => {
  restartVideo();

  // Use IntersectionObserver to detect when the component becomes visible
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting && entry.intersectionRatio > 0.5) {
          restartVideo();
        }
      });
    },
    {
      threshold: 0.5,
    }
  );

  if (videoRef.value) {
    observer.observe(videoRef.value);
  }
});

onUnmounted(() => {
  if (observer) {
    observer.disconnect();
  }
});
</script>

<style scoped>
.video-container {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100vw;
  height: 100vh;
  z-index: -1;
  overflow: hidden;
  margin: 0;
  padding: 0;
}

.video-element {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 100%;
  height: 100%;
  min-width: 100%;
  min-height: 100%;
  object-fit: cover;
  object-position: center;
  transform: translate(-50%, -50%);
  margin: 0;
  padding: 0;
}

.content-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100vw;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
  pointer-events: none;
  margin: 0;
  padding: 0;
}

.content-overlay > * {
  pointer-events: auto;
}
</style>
