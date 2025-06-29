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

    <!-- Lower Third Overlay -->
    <div class="lower-third-overlay" :class="{ 'content-fade-in': videoEnded && fadeOut }">
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

/* Lower Third Overlay - Professional broadcast style */
.lower-third-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 3rem 4rem 4rem 4rem;
  background: linear-gradient(
    to top,
    rgba(0, 0, 0, 0.8) 0%,
    rgba(0, 0, 0, 0.6) 50%,
    rgba(0, 0, 0, 0.2) 80%,
    transparent 100%
  );
  backdrop-filter: blur(4px);
  pointer-events: none;
  opacity: 1;
  transition: opacity v-bind(fadeDuration) ease-in-out;
}

.content-fade-in {
  opacity: 1;
}

/* Style content within lower third */
.lower-third-overlay > * {
  pointer-events: auto;
  color: white;
  text-shadow: 0 2px 8px rgba(0, 0, 0, 0.8);
  margin: 0;
}

/* Specific styling for headings in lower third */
.lower-third-overlay h1 {
  font-size: clamp(2rem, 4vw, 3.5rem);
  font-weight: 700;
  line-height: 1.1;
  margin-bottom: 0.5rem;
  color: white !important;
  text-shadow: 0 3px 12px rgba(0, 0, 0, 0.9);
}

.lower-third-overlay h2 {
  font-size: clamp(1.25rem, 2.5vw, 2rem);
  font-weight: 500;
  line-height: 1.2;
  margin-bottom: 0.5rem;
  color: rgba(255, 255, 255, 0.9) !important;
  text-shadow: 0 2px 8px rgba(0, 0, 0, 0.8);
}

.lower-third-overlay strong {
  color: #fbbf24 !important;
  text-shadow: 0 2px 8px rgba(0, 0, 0, 0.9);
}

/* Override any existing text colors for video overlay */
.lower-third-overlay .text-gray-900,
.lower-third-overlay .text-primary-600 {
  color: white !important;
}

.lower-third-overlay .text-center {
  text-align: center;
}

/* Background for text containers within lower third */
.lower-third-overlay .bg-white {
  background: rgba(0, 0, 0, 0.7) !important;
  backdrop-filter: blur(8px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}
</style>