---
layout: image
image: /screenshot-verified.png
backgroundSize: contain
---

<div class="relative h-full w-full">

  <!-- Certificate overlay in center-right -->
  <div class="absolute top-1/2 right-1/3 transform -translate-y-1/2 z-20 hidden">
    <div class="bg-white p-6 rounded-2xl shadow-2xl border-4 border-green-200 transform rotate-3 hover:rotate-0 transition-transform duration-300">
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