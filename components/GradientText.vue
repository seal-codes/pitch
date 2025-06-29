<template>
  <span :class="gradientClass" :style="gradientStyle">
    <slot />
  </span>
</template>

<script setup lang="ts">
import { computed } from 'vue'

interface Props {
  startColor?: string
  endColor?: string
  direction?: 'left-to-right' | 'right-to-left' | 'top-to-bottom' | 'bottom-to-top'
}

const props = withDefaults(defineProps<Props>(), {
  startColor: '#961a1a', // Secondary-500 (red)
  endColor: '#2ab5b5', // Primary-500 (teal)
  direction: 'left-to-right',
})

const gradientDirection = computed(() => {
  switch (props.direction) {
    case 'left-to-right': return 'to right'
    case 'right-to-left': return 'to left'
    case 'top-to-bottom': return 'to bottom'
    case 'bottom-to-top': return 'to top'
    default: return 'to right'
  }
})

const gradientClass = computed(() => 'gradient-text-chrome-fix')

const gradientStyle = computed(() => {
  return {
    background: `linear-gradient(${gradientDirection.value}, ${props.startColor}, ${props.endColor})`,
    WebkitBackgroundClip: 'text',
    WebkitTextFillColor: 'transparent',
    backgroundClip: 'text',
    display: 'inline-block',
    // Chrome fallback
    color: 'transparent',
    // Ensure text is selectable
    WebkitUserSelect: 'text',
    userSelect: 'text',
  }
})
</script>

<style scoped>
.gradient-text-chrome-fix {
  /* Chrome-specific fixes */
  -webkit-background-clip: text !important;
  -webkit-text-fill-color: transparent !important;
  background-clip: text !important;
  
  /* Fallback for older browsers */
  color: transparent;
  
  /* Ensure proper rendering */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  /* Force hardware acceleration */
  transform: translateZ(0);
  will-change: transform;
  
  /* Ensure text remains selectable */
  -webkit-user-select: text;
  -moz-user-select: text;
  -ms-user-select: text;
  user-select: text;
}

/* Chrome-specific media query fix */
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  .gradient-text-chrome-fix {
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-attachment: fixed;
  }
}

/* Additional Chrome version compatibility */
@supports (-webkit-background-clip: text) {
  .gradient-text-chrome-fix {
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
}

/* Fallback for browsers that don't support background-clip: text */
@supports not (-webkit-background-clip: text) {
  .gradient-text-chrome-fix {
    /* Fallback to solid color */
    color: v-bind('props.startColor') !important;
    background: none !important;
  }
}
</style>