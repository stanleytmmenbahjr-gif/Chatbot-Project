<template>
  <section id="partners" class="py-20 px-10 bg-gray-950">
    <h2 class="text-4xl font-bold text-orange-500 mb-10 text-center">Our Partners</h2>

    <div class="grid grid-cols-2 md:grid-cols-4 gap-8 items-center">
      <!-- Partner 1 -->
      <div 
        class="bg-gray-900 rounded-xl overflow-hidden text-center transform transition-all duration-500 hover:scale-105 hover:shadow-lg"
      >
        <img 
          src="../assets/icampus.png" 
          alt="Partner 1" 
          class="w-full h-40 object-cover mb-3"
        />
        <p class="text-white font-semibold mb-3">iCampus</p>
      </div>

      <!-- Partner 2 -->
      <div 
        class="bg-gray-900 rounded-xl overflow-hidden text-center transform transition-all duration-500 hover:scale-105 hover:shadow-lg"
      >
        <img 
          src="../assets/unipod.jpg" 
          alt="Partner 2" 
          class="w-full h-40 object-cover mb-3"
        />
        <p class="text-white font-semibold mb-3">UniPod-Liberia</p>
      </div>

      <!-- Partner 3 -->
      <div 
        class="bg-gray-900 rounded-xl overflow-hidden text-center transform transition-all duration-500 hover:scale-105 hover:shadow-lg"
      >
        <img 
          src="../assets/open source.jpg" 
          alt="Partner 3" 
          class="w-full h-40 object-cover mb-3"
        />
        <p class="text-white font-semibold mb-3">Open Source Liberia </p>
      </div>

      <!-- Partner 4 -->
      <div 
        class="bg-gray-900 rounded-xl overflow-hidden text-center transform transition-all duration-500 hover:scale-105 hover:shadow-lg"
      >
        <img 
          src="../assets/UNDP.jpeg" 
          alt="Partner 4" 
          class="w-full h-40 object-cover mb-3"
        />
        <p class="text-white font-semibold mb-3">UNDP</p>
      </div>
    </div>
  </section>
</template>

<script>
export default { name: 'PartnersSection' }
</script>
