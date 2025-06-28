---
layout: cover
---

<div class="relative h-full w-full">
  <!-- Full-size background image -->
  <div class="absolute inset-0 w-full h-full">
    <img 
      src="/screenshot-seal-document.png" 
      alt="seal.codes interface" 
      class="w-full h-full object-cover"
    />
    <!-- Overlay for better text readability -->
    <div class="absolute inset-0 bg-black bg-opacity-20"></div>
  </div>
  

  <!-- Badge popover in lower right -->
  <div class="absolute bottom-8 right-8 z-20">
    <div class="bg-gradient-to-r from-green-500 to-emerald-500 text-white px-6 py-4 rounded-2xl shadow-2xl transform rotate-3 hover:rotate-0 transition-transform duration-300">
      <div class="flex items-center space-x-3">
        <lucide-shield-check class="w-8 h-8" />
        <div class="text-right">
          <div class="font-bold text-lg leading-tight">No private keys</div>
          <div class="font-bold text-lg leading-tight">No certificates</div>
          <div class="font-bold text-lg leading-tight">No complexity</div>
        </div>
      </div>
      <!-- Badge tail -->
      <div class="absolute -bottom-2 right-6 w-0 h-0 border-l-4 border-r-4 border-t-8 border-l-transparent border-r-transparent border-t-emerald-500"></div>
    </div>
  </div>
</div>

<!--
Here's how simple it is: Upload your document, login with a social account you already have - Google, GitHub, whatever you use - and get your digital seal. That's it. No private keys, no certificates, no technical complexity. The seal embeds directly into your document as a QR code that anyone can verify.
-->