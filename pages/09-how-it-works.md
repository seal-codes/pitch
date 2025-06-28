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
  
  <!-- Content overlay in top-left -->
  <div class="absolute top-8 left-8 z-10">
    <div class="bg-white bg-opacity-95 p-8 rounded-2xl shadow-2xl max-w-md backdrop-blur-sm">
      <h1 class="text-4xl font-bold mb-6 text-gray-900">How It Works</h1>
      <h2 class="mb-8 text-brand-primary text-2xl font-semibold">Simple as 1-2-3</h2>
      
      <div class="space-y-6">
        <div class="flex items-center space-x-4">
          <div class="w-12 h-12 bg-gradient-to-br from-primary-500 to-primary-400 text-white rounded-full flex items-center justify-center font-bold text-xl shadow-lg">1</div>
          <div>
            <div class="text-lg font-semibold text-gray-800">Upload document</div>
            <div class="text-sm text-gray-600">Any PDF, image, or file</div>
          </div>
        </div>
        
        <div class="flex items-center space-x-4">
          <div class="w-12 h-12 bg-gradient-to-br from-primary-500 to-primary-400 text-white rounded-full flex items-center justify-center font-bold text-xl shadow-lg">2</div>
          <div>
            <div class="text-lg font-semibold text-gray-800">Login socially</div>
            <div class="text-sm text-gray-600">Google, GitHub, etc.</div>
          </div>
        </div>
        
        <div class="flex items-center space-x-4">
          <div class="w-12 h-12 bg-gradient-to-br from-primary-500 to-primary-400 text-white rounded-full flex items-center justify-center font-bold text-xl shadow-lg">3</div>
          <div>
            <div class="text-lg font-semibold text-gray-800">Get your seal</div>
            <div class="text-sm text-gray-600">QR code embedded</div>
          </div>
        </div>
      </div>
    </div>
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