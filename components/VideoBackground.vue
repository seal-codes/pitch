<template>
  <div class="absolute inset-0 w-full h-full">
    <video
      ref="videoRef"
      autoplay
      muted
      class="absolute inset-0 w-full h-full object-cover"
      :poster="poster"
    >
      <source :src="src" type="video/mp4" />
      Your browser does not support the video tag.
    </video>

    <div class="absolute inset-0 flex items-center justify-center">
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
/* Ensure the component takes full viewport height */
.absolute.inset-0 {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}
</style>
