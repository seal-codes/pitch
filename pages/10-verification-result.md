---
layout: cover
---

<div class="relative h-full w-full">
  <!-- Full-size background image -->
  <div class="absolute inset-0 w-full h-full">
    <img 
      src="/screenshot-verified.png" 
      alt="Verification interface" 
      class="w-full h-full object-cover"
    />
    <!-- Overlay for better text readability -->
    <div class="absolute inset-0 bg-black bg-opacity-25"></div>
  </div>
  
  <!-- Content overlay -->
  <div class="relative z-10 h-full flex flex-col justify-center pl-16 pr-96">
    <div class="bg-white bg-opacity-95 p-8 rounded-2xl shadow-2xl backdrop-blur-sm max-w-2xl">
      <h1 class="text-5xl font-bold mb-6 text-brand-primary brand-accent">The Result: Verified Trust</h1>
      <h2 class="text-3xl mb-8 text-brand-secondary">Instant Verification</h2>
      <p class="text-2xl leading-relaxed mb-8 text-gray-700">
        Anyone can verify authenticity by scanning the QR code
      </p>
      <div class="space-y-4 text-xl">
        <div class="flex items-center space-x-4">
          <lucide-check-circle class="text-primary-500 text-2xl" />
          <span class="font-medium text-gray-800">Who created it</span>
        </div>
        <div class="flex items-center space-x-4">
          <lucide-check-circle class="text-primary-500 text-2xl" />
          <span class="font-medium text-gray-800">When it was sealed</span>
        </div>
        <div class="flex items-center space-x-4">
          <lucide-check-circle class="text-primary-500 text-2xl" />
          <span class="font-medium text-gray-800">Hasn't been tampered with</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Certificate overlay in center-right -->
  <div class="absolute top-1/2 right-16 transform -translate-y-1/2 z-20">
    <div class="bg-white p-6 rounded-2xl shadow-2xl border-4 border-green-200 transform rotate-3 hover:rotate-0 transition-transform duration-300">
      <div class="flex items-center justify-center mb-4">
        <lucide-award class="w-8 h-8 text-green-600 mr-2" />
        <span class="text-lg font-bold text-green-800">Verification Certificate</span>
      </div>
      <img 
        src="/screenshot-verified-details.png" 
        alt="Verification details certificate" 
        class="rounded-lg shadow-md max-w-sm border border-gray-200"
      />
      <!-- Certificate seal -->
      <div class="absolute -top-3 -right-3 w-12 h-12 bg-green-500 rounded-full flex items-center justify-center shadow-lg">
        <lucide-check class="w-6 h-6 text-white" />
      </div>
    </div>
  </div>
</div>

<!--
When someone receives your document, they simply scan the QR code. They instantly see who created it, when it was sealed, and can verify it hasn't been tampered with. It's like having a digital handshake embedded right in your content.
-->