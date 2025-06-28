---
# Slidev Configuration
theme: default
aspectRatio: 16/9
canvasWidth: 1920
title: 'seal.codes - Digital Seals for the Modern Age'
titleTemplate: '%s - Hackathon Pitch'
info: |
  ## seal.codes Hackathon Pitch
  
  Revolutionary digital authenticity solution using QR code attestations
  linked to social identities. Bringing visible trust marks to the digital age.

# Fonts
fonts:
  sans: 'Inter, system-ui, sans-serif'
  serif: 'Georgia, serif'
  mono: 'JetBrains Mono, monospace'

# Styling
css: unocss
colorSchema: auto

# Features
drawings:
  enabled: false
  persist: false

# Export options
download: true
exportFilename: 'seal-codes-pitch'

# Presenter mode
presenter: true
---

<style>
/* Custom styling for seal.codes presentation */
.slidev-layout {
  --uno: 'font-sans';
}

/* Cover slide styling */
.slidev-layout.cover {
  --uno: 'text-white';
  background: linear-gradient(135deg, #1e3a8a 0%, #3730a3 50%, #1e1b4b 100%);
}

/* Image layouts */
.slidev-layout.image-right,
.slidev-layout.image-left {
  --uno: 'text-gray-900 dark:text-gray-100';
}

/* Typography */
h1 {
  --uno: 'text-4xl md:text-6xl font-bold leading-tight mb-8';
}

h2 {
  --uno: 'text-2xl md:text-4xl font-semibold leading-tight mb-6';
}

h3 {
  --uno: 'text-xl md:text-2xl font-medium leading-tight mb-4';
}

/* Slide content spacing */
.slidev-layout > * {
  --uno: 'max-w-4xl mx-auto';
}

/* Speaker notes styling */
.slidev-presenter-notes {
  --uno: 'text-base leading-relaxed';
}

/* Video backgrounds */
.video-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
}

.video-overlay {
  position: relative;
  z-index: 1;
  background: rgba(0, 0, 0, 0.4);
  padding: 2rem;
  border-radius: 1rem;
}
</style>

---
layout: cover
---

<div class="flex flex-col items-center justify-center h-full text-center">
  <img src="/logo.svg" alt="seal.codes logo" class="w-32 h-32 mb-8" />
  <h1 class="text-6xl font-bold mb-4">seal.codes</h1>
  <h2 class="text-2xl font-light opacity-90">Digital Seals for the Modern Age</h2>
  <div class="mt-8 text-lg opacity-75">
    Hackathon Innovation Showcase
  </div>
</div>

<!--
Thank you for your time today. I want to talk about something we all engage in every single moment of our lives: human interaction. And at the heart of every interaction lies one fundamental element - trust. Today I'll show you how we're bringing that trust back to our digital world with seal.codes.
-->

---
layout: cover
background: /people-shaking-hands.mp4
---

<div class="flex items-center justify-center h-full">
  <div class="bg-black bg-opacity-50 p-12 rounded-2xl text-center">
    <h1>The Foundation of Human Interaction: <strong class="text-blue-300">Trust</strong></h1>
  </div>
</div>

<!--
What makes us as humans so unique is the intricate way we interact. We build societies, create art, and conduct business. And every single one of these interactions, from a simple conversation to a global transaction, is built on a fundamental, invisible foundation: Trust.
-->

---
layout: cover
background: /King applying a seal.mp4
---

<div class="flex items-center justify-center h-full">
  <div class="bg-black bg-opacity-50 p-12 rounded-2xl text-center">
    <h1>For millennia, seals provided <strong class="text-amber-300">visible proof</strong> of authenticity</h1>
  </div>
</div>

<!--
For millennia, humans solved this with visible marks of authenticity. Royal seals pressed into wax instantly communicated who stood behind a document and protected against unauthorized modifications. These weren't just decorative - they were the foundation of commerce, law, and society.
-->

---
layout: cover
image: /digital-uncertainty.png
---

<div class="flex items-center justify-center h-full">
  <div class="bg-black bg-opacity-60 p-12 rounded-2xl text-center">
    <h1>In the digital space, that foundation is <strong class="text-red-400">crumbling</strong></h1>
  </div>
</div>

<!--
But in the digital space, that foundation is crumbling. The very openness that allows us to connect globally has also created a crisis of trust. We are constantly forced to ask: Is this real? Is this authentic? Who is truly behind this? The traditional signals of trust have been lost in a sea of anonymous, easily duplicated content.
-->

---
layout: default
---

<div class="h-full relative bg-gradient-to-br from-gray-50 to-gray-100">
<div class="h-full flex flex-col justify-center pr-64 pl-16">
<h1 class="text-5xl font-bold mb-6 text-red-600">The Creator's Dilemma</h1>
<h2 class="text-3xl mb-8">Meet Sarah</h2>
<p class="text-2xl leading-relaxed mb-8">
Her interaction with the world is through her art.
</p>
<p class="text-xl opacity-80 mb-12">
When her work is stolen and her ownership is erased, 
the trust between her and her audience is broken.
</p>
<img src="/social-media-unauthorized-copy.png" alt="Stolen content example" class="rounded-lg shadow-lg max-w-md" />
</div>
<div class="absolute bottom-8 right-8 transform rotate-3">
<div class="bg-white p-3 shadow-2xl rounded">
<img src="/sarah-portrait.png" alt="Sarah portrait" class="w-40 h-52 object-cover rounded" />
<div class="text-center mt-2 text-gray-700 font-medium">Sarah</div>
</div>
</div>
</div>

<!--
This is Sarah. She's a creator. Her interaction with the world is through her art. But when her work is stolen and her ownership is erased, the trust between her and her audience is broken. She loses credit, income, and the digital world loses a piece of its integrity. This happens millions of times every day.
-->

---
layout: default
---

<div class="h-full relative bg-gradient-to-br from-orange-50 to-orange-100">
<div class="h-full flex flex-col justify-center pr-64 pl-16">
<h1 class="text-5xl font-bold mb-6 text-orange-600">The Buyer's Gamble</h1>
<h2 class="text-3xl mb-8">Meet Alex</h2>
<p class="text-2xl leading-relaxed mb-8">
He wants to buy something online, but the marketplace is filled with doubt.
</p>
<p class="text-xl opacity-80 mb-12">
He's forced to gamble, unsure if a seller is legitimate or a scam.
</p>
<img src="/two-advertisements-with-and-without-seld-code.png" alt="Marketplace comparison" class="rounded-lg shadow-lg max-w-md" />
</div>
<div class="absolute bottom-8 right-8 transform -rotate-2">
<div class="bg-white p-3 shadow-2xl rounded">
<img src="/alex-portrait.png" alt="Alex portrait" class="w-40 h-52 object-cover rounded" />
<div class="text-center mt-2 text-gray-700 font-medium">Alex</div>
</div>
</div>
</div>

<!--
This is Alex. His interaction is a transaction—he wants to buy something online. But the digital marketplace is filled with doubt. He's forced to gamble, unsure if a seller is legitimate or a scam. This lack of trust creates friction, prevents commerce, and costs billions in fraud annually.
-->

---
layout: cover
---

<div class="flex items-center justify-center h-full">
<div class="text-center">
<h1 class="mb-8">The Expert's Curse</h1>
<h2 class="text-3xl font-light opacity-90 mb-16">
Powerful solutions existed, but were only for the few
</h2>
<div class="grid grid-cols-4 gap-12 max-w-4xl mx-auto">
<div class="text-center">
<lucide-shield-check class="text-6xl mb-4 mx-auto opacity-60" />
<div class="text-xl font-medium">Certificates Authorities</div>
</div>
<div class="text-center">
<lucide-key class="text-6xl mb-4 mx-auto opacity-60" />
<div class="text-xl font-medium">PKI</div>
</div>
<div class="text-center">
<lucide-settings class="text-6xl mb-4 mx-auto opacity-60" />
<div class="text-xl font-medium">Complex Setup</div>
</div>
<div class="text-center">
<lucide-cloud class="text-6xl mb-4 mx-auto opacity-60" />
<div class="text-xl font-medium">Cloud based</div>
</div>
</div>
</div>
</div>

<!--
For decades, brilliant minds have tried to solve this. We've had cryptographic solutions like PGP and complex Trust Chains with PKI. But these tools have a fatal flaw: they were built by experts, for experts. They require complex setup, key management, and a level of technical understanding that puts them out of reach for almost everyone.
-->

---
layout: cover
---

<div class="flex items-center justify-center h-full">
<div class="text-center">
<h1 class="mb-8">A Return to Clarity</h1>
<h2 class="text-3xl font-light opacity-90 mb-16">
We believe the solution isn't more complexity,<br>
but a return to a <strong class="text-blue-300">visible mark of trust</strong>
</h2>
<div class="flex items-center justify-center space-x-16">
<div class="text-center opacity-75">
<img src="/wax-seal.png" alt="Ancient seal" class="w-32 h-32 mx-auto mb-6 rounded-full" />
<div class="text-xl font-medium">Ancient</div>
</div>
<lucide-arrow-right class="text-8xl opacity-50" />
<div class="text-center">
<div class="w-32 h-32 mx-auto mb-6 bg-white rounded-lg flex items-center justify-center">
<lucide-smartphone class="text-5xl text-blue-500" />
</div>
<div class="text-xl font-medium text-blue-300">Digital</div>
</div>
</div>
</div>
</div>

<!--
seal.codes was created to solve this. We believe the solution isn't to build more complex systems, but to return to the simple clarity of a visible mark of trust. We're bringing the simple, elegant concept of the seal to the digital age - but powered by modern technology.
-->

---
layout: image-left
image: /screenshot-seal-document.png
---

# How It Works

<div class="pl-8">
<h2 class="mb-12 text-blue-600 text-3xl">Simple as 1-2-3</h2>
<div class="space-y-10">
<div class="flex items-center space-x-6">
<div class="w-16 h-16 bg-blue-500 text-white rounded-full flex items-center justify-center font-bold text-2xl">1</div>
<div>
<div class="text-2xl font-semibold mb-2">Upload your document</div>
<div class="text-xl opacity-80">Any PDF, image, or file</div>
</div>
</div>
<div class="flex items-center space-x-6">
<div class="w-16 h-16 bg-blue-500 text-white rounded-full flex items-center justify-center font-bold text-2xl">2</div>
<div>
<div class="text-2xl font-semibold mb-2">Login with social account</div>
<div class="text-xl opacity-80">Google, GitHub, or any provider you already use</div>
</div>
</div>
<div class="flex items-center space-x-6">
<div class="w-16 h-16 bg-blue-500 text-white rounded-full flex items-center justify-center font-bold text-2xl">3</div>
<div>
<div class="text-2xl font-semibold mb-2">Get your digital seal</div>
<div class="text-xl opacity-80">QR code embedded directly in your document</div>
</div>
</div>
</div>
<div class="mt-16 p-8 bg-blue-50 rounded-lg">
<div class="text-xl font-bold text-blue-800">No private keys. No certificates. No technical complexity.</div>
</div>
</div>

<!--
Here's how simple it is: Upload your document, login with a social account you already have - Google, GitHub, whatever you use - and get your digital seal. That's it. No private keys, no certificates, no technical complexity. The seal embeds directly into your document as a QR code that anyone can verify.
-->

---
layout: image-right
image: /screenshot-verified.png
---

# The Result: Verified Trust

<div class="flex flex-col justify-center h-full">
<h2 class="mb-8 text-green-600 text-3xl">Instant Verification</h2>
<p class="text-2xl leading-relaxed mb-12">
Anyone can verify authenticity by scanning the QR code
</p>
<div class="space-y-6 text-xl">
<div class="flex items-center space-x-4">
<lucide-check-circle class="text-green-500 text-3xl" />
<span class="font-medium">Who created it</span>
</div>
<div class="flex items-center space-x-4">
<lucide-check-circle class="text-green-500 text-3xl" />
<span class="font-medium">When it was sealed</span>
</div>
<div class="flex items-center space-x-4">
<lucide-check-circle class="text-green-500 text-3xl" />
<span class="font-medium">Hasn't been tampered with</span>
</div>
</div>
<div class="mt-12">
<img src="/screenshot-verified-details.png" alt="Verification details" class="rounded-lg shadow-lg" />
</div>
</div>

<!--
When someone receives your document, they simply scan the QR code. They instantly see who created it, when it was sealed, and can verify it hasn't been tampered with. It's like having a digital handshake embedded right in your content.
-->

---
layout: default
---

<div class="h-full relative bg-gradient-to-br from-purple-50 to-purple-100">
<div class="h-full flex flex-col justify-center pr-64 pl-16">
<h1 class="text-5xl font-bold mb-6 text-purple-600">Sarah's Success</h1>
<h2 class="text-3xl mb-12 text-purple-600">The Creator Empowered</h2>
<p class="text-2xl leading-relaxed mb-12">
Sarah now proudly declares:<br>
<strong>"This is mine. I stand behind it."</strong>
</p>
<p class="text-xl opacity-80 mb-16">
She's restoring trust in her creative interactions, 
and her audience knows they're seeing authentic work.
</p>
<div class="bg-purple-100 p-8 rounded-lg max-w-md">
<img src="/screenshot-sealed-document.png" alt="Sarah's sealed artwork" class="rounded-lg shadow-md" />
</div>
</div>
<div class="absolute bottom-8 right-8 transform rotate-2">
<div class="bg-white p-3 shadow-2xl rounded">
<img src="/sarah-portrait.png" alt="Sarah portrait" class="w-40 h-52 object-cover rounded" />
<div class="text-center mt-2 text-gray-700 font-medium">Sarah <lucide-sparkles class="inline w-5 h-5" /></div>
</div>
</div>
</div>

<!--
Now Sarah can embed a visible, verifiable seal directly onto her work. She's not just protecting her art; she's proudly declaring, 'This is mine. I stand behind it.' She's restoring the trust in her creative interactions, and her audience knows they're seeing authentic work.
-->

---
layout: default
---

<div class="h-full relative bg-gradient-to-br from-orange-50 to-orange-100">
<div class="h-full flex flex-col justify-center pr-64 pl-16">
<h1 class="text-5xl font-bold mb-6 text-orange-600">Alex's Confidence</h1>
<h2 class="text-3xl mb-12 text-orange-600">The Buyer Protected</h2>
<p class="text-2xl leading-relaxed mb-12">
Alex can now transact with confidence
</p>
<p class="text-xl opacity-80 mb-16">
The seal acts as a digital handshake, removing doubt 
and preventing fraud.
</p>
<div class="bg-orange-100 p-8 rounded-lg max-w-sm">
<div class="text-center">
<lucide-handshake class="text-6xl mb-6 mx-auto text-orange-600" />
<p class="text-xl font-semibold mb-2">Digital Handshake</p>
<p class="text-lg opacity-75">Instant trust verification</p>
</div>
</div>
</div>
<div class="absolute bottom-8 right-8 transform -rotate-1">
<div class="bg-white p-3 shadow-2xl rounded">
<img src="/alex-portrait.png" alt="Alex portrait" class="w-40 h-52 object-cover rounded" />
<div class="text-center mt-2 text-gray-700 font-medium">Alex <lucide-thumbs-up class="inline w-5 h-5" /></div>
</div>
</div>
</div>

<!--
The seal acts as Alex's digital handshake. By scanning it, he can instantly verify that the seller is real and legitimate. It removes the doubt, prevents the fraud, and allows a trusted transaction to take place, just as it would in the physical world.
-->

---
layout: cover
---

<div class="flex items-center justify-center h-full">
<div class="text-center">
<h1 class="mb-12">Innovation Showcase</h1>
<div class="mb-16">
<div class="text-8xl font-bold text-blue-400 mb-6">88%</div>
<h2 class="text-3xl font-light">Built with AI assistance</h2>
</div>
<h3 class="text-2xl opacity-90 mb-12">
Genuine innovation, not another clone
</h3>
<div class="grid grid-cols-2 gap-12 max-w-3xl mx-auto">
<div class="text-center p-8 bg-white bg-opacity-10 rounded-lg">
<lucide-rocket class="text-6xl mb-4 mx-auto" />
<div class="text-xl font-semibold mb-2">bolt.new</div>
<div class="text-lg opacity-75">AI-powered development</div>
</div>
<div class="text-center p-8 bg-white bg-opacity-10 rounded-lg">
<lucide-lightbulb class="text-6xl mb-4 mx-auto" />
<div class="text-xl font-semibold mb-2">Novel Solution</div>
<div class="text-lg opacity-75">Not just another app</div>
</div>
</div>
</div>
</div>

<!--
This isn't just another app - this represents genuine innovation. Built with 88% AI assistance using bolt.new, seal.codes demonstrates what's possible when we combine human creativity with AI capability. We didn't build another todo app or social network clone - we solved a fundamental problem that's existed since the dawn of the internet.
-->

---
layout: cover
---

<div class="flex items-center justify-center h-full">
<div class="text-center">
<h1 class="mb-12">Our Vision</h1>
<h2 class="text-3xl font-light opacity-90 mb-16">
Restoring trust to our digital world,<br>
<strong class="text-blue-300">one seal at a time</strong>
</h2>
<div class="relative">
<div class="absolute inset-0 bg-gradient-to-r from-blue-500 to-purple-500 rounded-full blur-3xl opacity-20"></div>
<div class="relative grid grid-cols-3 gap-12 max-w-4xl mx-auto">
<div class="text-center">
<lucide-globe class="text-6xl mb-6 mx-auto" />
<div class="text-xl font-semibold mb-2">Global</div>
<div class="text-lg opacity-75">Worldwide trust network</div>
</div>
<div class="text-center">
<lucide-link class="text-6xl mb-6 mx-auto" />
<div class="text-xl font-semibold mb-2">Connected</div>
<div class="text-lg opacity-75">Social identity powered</div>
</div>
<div class="text-center">
<lucide-users class="text-6xl mb-6 mx-auto" />
<div class="text-xl font-semibold mb-2">Empowering</div>
<div class="text-lg opacity-75">Individual ownership</div>
</div>
</div>
</div>
</div>
</div>

<!--
Our vision isn't to create yet another complex, centralized platform. It's about empowerment. It's about giving every user the ability to leverage the social identities they already have to prove ownership and authenticity. We're putting the power of a trusted seal back into the hands of the individual.
-->

---
layout: cover
---

<div class="flex flex-col items-center justify-center h-full text-center">
<img src="/logo.svg" alt="seal.codes logo" class="w-40 h-40 mb-8" />
<h1 class="text-5xl font-bold mb-6">seal.codes</h1>
<h2 class="text-2xl font-light mb-12">
Add a seal. Share with confidence.
</h2>
<div class="text-lg opacity-75 mb-8">
www.seal.codes
</div>
<div class="text-base opacity-60">
Thank you
</div>
</div>

<!--
We invite you to help us restore trust to our digital world. seal.codes - Add a seal. Share with confidence. Thank you.
-->
