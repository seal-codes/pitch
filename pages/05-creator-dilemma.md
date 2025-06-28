---
layout: default
---

<div class="h-full relative bg-gradient-to-br from-gray-50 to-gray-100 overflow-hidden">
<div class="h-full flex flex-col justify-center pl-16 pr-8">
<h1 class="text-5xl font-bold mb-6 text-secondary-500 brand-accent">The Creator's Dilemma</h1>
<h2 class="text-3xl mb-8 text-gray-800">Meet Sarah</h2>

<!-- Story State 1: Working Hard -->
<div id="story-working" class="transition-all duration-1000 ease-in-out">
<p class="text-2xl leading-relaxed mb-8 text-gray-700">
Sarah works tirelessly on her art, pouring her heart into every piece.
</p>
<p class="text-xl text-gray-600 mb-12">
Each creation represents hours of dedication, skill, and personal expression.
</p>
<div class="max-w-2xl">
<img src="/collage-assets-created-physical-world.png" alt="Sarah working on her art" class="rounded-lg shadow-lg border border-gray-200 w-full cursor-pointer hover:shadow-xl transition-shadow duration-300" onclick="revealTheft()" />
<p class="text-center mt-4 text-gray-500 italic">Click to see what happens next...</p>
</div>
</div>

<!-- Story State 2: Theft Revealed (Hidden Initially) -->
<div id="story-theft" class="hidden transition-all duration-1000 ease-in-out">
<p class="text-2xl leading-relaxed mb-8 text-gray-700">
But then her work is stolen and her ownership is erased.
</p>
<p class="text-xl text-gray-600 mb-12">
The trust between her and her audience is <strong class="text-secondary-500">broken</strong>.
</p>
<div class="max-w-2xl">
<img src="/social-media-unauthorized-copy.png" alt="Stolen content example" class="rounded-lg shadow-lg border border-gray-200 w-full" />
</div>
</div>
</div>

<!-- Sarah Portrait - Changes on Click -->
<div class="absolute bottom-8 right-8 transform rotate-3 transition-all duration-1000 ease-in-out">
<div class="polaroid">
<img id="sarah-portrait" src="/sarah-portrait.png" alt="Sarah portrait" class="w-40 h-52 object-cover rounded transition-all duration-500" />
<div class="text-center mt-2 text-gray-700 font-medium">
<span id="sarah-name">Sarah</span>
<span id="sarah-emoji" class="ml-1">😊</span>
</div>
</div>
</div>
</div>

<script>
function revealTheft() {
  // Hide working story
  const workingStory = document.getElementById('story-working');
  const theftStory = document.getElementById('story-theft');
  const sarahPortrait = document.getElementById('sarah-portrait');
  const sarahEmoji = document.getElementById('sarah-emoji');
  
  // Fade out working story
  workingStory.style.opacity = '0';
  workingStory.style.transform = 'translateY(-20px)';
  
  setTimeout(() => {
    workingStory.classList.add('hidden');
    theftStory.classList.remove('hidden');
    
    // Fade in theft story
    setTimeout(() => {
      theftStory.style.opacity = '1';
      theftStory.style.transform = 'translateY(0)';
    }, 100);
    
    // Change Sarah's portrait to show distress
    sarahPortrait.style.filter = 'sepia(20%) saturate(120%) hue-rotate(-10deg)';
    sarahEmoji.textContent = '😠';
    
    // Add shake animation to portrait
    sarahPortrait.parentElement.parentElement.style.animation = 'shake 0.5s ease-in-out';
  }, 500);
}

// Add shake animation
const style = document.createElement('style');
style.textContent = `
  @keyframes shake {
    0%, 100% { transform: rotate(3deg) translateX(0); }
    25% { transform: rotate(1deg) translateX(-2px); }
    75% { transform: rotate(5deg) translateX(2px); }
  }
`;
document.head.appendChild(style);
</script>

<!--
This is Sarah. She's a creator. Her interaction with the world is through her art. She works tirelessly, pouring her heart into every piece. But when her work is stolen and her ownership is erased, the trust between her and her audience is broken. She loses credit, income, and the digital world loses a piece of its integrity. This happens millions of times every day.
-->