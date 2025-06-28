<template>
  <div class="absolute inset-0 w-full h-full">
    <video 
      autoplay 
      muted 
      class="absolute inset-0 w-full h-full object-cover"
      :poster="poster"
    >
      <source :src="src" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    
    <div class="absolute inset-0 flex items-center justify-center">
      <slot />
    </div>
  </div>
</template>

<script setup>
defineProps({
  src: {
    type: String,
    required: true
  },
  poster: {
    type: String,
    default: ''
  }
})
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