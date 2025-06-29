<template>
  <div class="video-container">
    <video 
      ref="videoRef" 
      autoplay 
      muted 
      playsinline 
      class="video-element" 
      :class="{ 'video-fade-out': videoEnded && fadeOut }"
      :poster="poster"
      @ended="handleVideoEnd"
    >
      <source :src="src" type="video/mp4" />
      Your browser does not support the video tag.
    </video>

    <div class="content-overlay" :class="{ 'content-fade-in': videoEnded && fadeOut }">
      <slot />
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted, nextTick } from "vue";

const props = defineProps({
  src: {
    type: String,
    required: true,
  },
  poster: {
    type: String,
    default: "",
  },
  width: {
    type: String,
    default: "stretch",
  },
  height: {
    type: String,
    default: "max-content",
  },
  fadeOut: {
    type: Boolean,
    default: false,
  },
  fadeDuration: {
    type: String,
    default: "1s",
  },
});

const videoRef = ref(null);
const videoEnded = ref(false);
let observer = null;

const handleVideoEnd = () => {
  if (props.fadeOut) {
    videoEnded.value = true;
  }
};

const restartVideo = async () => {
  if (videoRef.value) {
    try {
      videoRef.value.currentTime = 0;
      videoEnded.value = false;
      await videoRef.value.play();
    } catch (error) {
      console.log("Video autoplay prevented:", error);
    }
  }
};

onMounted(async () => {
  await nextTick();

  // Initial play attempt
  setTimeout(() => {
    restartVideo();
  }, 100);

  // Use IntersectionObserver for slide transitions
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting && entry.intersectionRatio > 0.3) {
          restartVideo();
        } else {
          // Pause video when not visible to save resources
          if (videoRef.value && !videoRef.value.paused) {
            videoRef.value.pause();
          }
        }
      });
    },
    {
      threshold: [0.3, 0.7],
      rootMargin: "50px",
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
  if (videoRef.value) {
    videoRef.value.pause();
  }
});
</script>

<style scoped>
.video-container {
  position: relative;
  width: v-bind(width);
  height: v-bind(height);
  overflow: hidden;
  border-radius: 8px;
}

.video-element {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: opacity v-bind(fadeDuration) ease-in-out;
}

.video-fade-out {
  opacity: 0;
}

.content-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  pointer-events: none;
  opacity: 0;
  transition: opacity v-bind(fadeDuration) ease-in-out;
}

.content-fade-in {
  opacity: 1;
}

.content-overlay > * {
  pointer-events: auto;
  width: 100%;
  height: 100%;
}
</style>