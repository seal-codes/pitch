---
layout: cover
---

<div class="relative w-full h-full">
  <!-- Full-page screenshot background -->
  <div class="absolute inset-0 w-full h-full">
    <img 
      src="/screenshot-verified.png" 
      alt="Verification result screenshot" 
      class="w-full h-full object-cover"
    />
  </div>
  
  <!-- Stamped popover overlay -->
  <div class="absolute top-1/4 left-1/2 transform -translate-x-1/2 -translate-y-1/4">
    <div class="stamped-popover">
      <div class="stamp-border">
        <div class="stamp-content">
          <h1 class="text-4xl font-bold mb-6 text-gray-900">The Result: Verified Trust</h1>
          <div class="space-y-4 text-xl text-gray-800">
            <div class="flex items-center space-x-4">
              <lucide-check-circle class="text-primary-500 text-3xl flex-shrink-0" />
              <span class="font-medium">Who created it</span>
            </div>
            <div class="flex items-center space-x-4">
              <lucide-check-circle class="text-primary-500 text-3xl flex-shrink-0" />
              <span class="font-medium">When it was sealed</span>
            </div>
            <div class="flex items-center space-x-4">
              <lucide-check-circle class="text-primary-500 text-3xl flex-shrink-0" />
              <span class="font-medium">Hasn't been tampered with</span>
            </div>
          </div>
          <div class="mt-8 p-4 bg-primary-50 rounded-lg border-l-4 border-primary-500">
            <p class="text-lg font-semibold text-primary-800">
              No private keys. No certificates. No technical complexity.
            </p>
          </div>
        </div>
      </div>
      <!-- Stamp effect elements -->
      <div class="stamp-shadow"></div>
      <div class="stamp-texture"></div>
    </div>
  </div>
  
  <!-- Secondary screenshot for context -->
  <div class="absolute bottom-8 right-8 transform rotate-2">
    <div class="bg-white p-2 rounded-lg shadow-xl border-2 border-gray-200">
      <img 
        src="/screenshot-verified-details.png" 
        alt="Verification details" 
        class="w-64 h-auto rounded"
      />
      <div class="text-center mt-2 text-sm text-gray-600 font-medium">
        Instant verification details
      </div>
    </div>
  </div>
</div>

<!--
When someone receives your document, they simply scan the QR code. They instantly see who created it, when it was sealed, and can verify it hasn't been tampered with. It's like having a digital handshake embedded right in your content.
-->