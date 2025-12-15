<template>
  <section
    id="info"
    class="py-28 px-10 bg-gray-950 flex flex-col gap-16 items-center"
  >

    <!-- What We Do -->
    <div
      class="max-w-4xl w-full p-10 bg-gray-900/60 backdrop-blur-xl rounded-2xl
             border border-gray-800 shadow-lg animate-fadeInUp"
    >
      <h2 class="text-4xl font-bold text-orange-500 mb-6 tracking-tight">
        What We Do
      </h2>

      <p class="text-gray-300 leading-relaxed text-lg">
        Orange Digital Center Liberia empowers young people through digital skills,
        startup incubation, coding, creativity, and innovation — building real
        opportunities and real solutions for Liberia.
      </p>
    </div>

    <!-- Our Pillars -->
    <div
      class="max-w-4xl w-full p-10 bg-gray-900/60 backdrop-blur-xl rounded-2xl
             border border-gray-800 shadow-lg animate-fadeInUp"
      style="animation-delay: 0.2s"
    >
      <h3 class="text-2xl font-semibold text-orange-400 mb-8 text-center">
        Our Pillars
      </h3>

      <!-- Slider -->
      <div class="relative overflow-hidden">
        <div
          class="flex transition-transform duration-700 ease-in-out"
          :style="{ transform: `translateX(-${activeIndex * 100}%)` }"
        >
          <div
            v-for="(pillar, index) in pillars"
            :key="index"
            class="min-w-full flex justify-center"
          >
            <div
              class="w-72 h-40 bg-gray-950 border border-gray-800 rounded-xl
                     flex items-center justify-center text-xl font-medium
                     text-gray-300 hover:text-orange-400 transition"
            >
              {{ pillar }}
            </div>
          </div>
        </div>
      </div>

      <!-- Navigation Dots -->
      <div class="flex justify-center gap-3 mt-8">
        <span
          v-for="(pillar, index) in pillars"
          :key="index"
          @click="activeIndex = index"
          class="w-3 h-3 rounded-full cursor-pointer transition"
          :class="activeIndex === index ? 'bg-orange-500' : 'bg-gray-700'"
        ></span>
      </div>
    </div>

  </section>
</template>

<script>
export default {
  name: "InfoSection",
  data() {
    return {
      activeIndex: 0,
      pillars: [
        "Digital Training",
        "Startup Incubation",
        "Coding School",
        "Digital Fabrication Lab"
      ]
    };
  },
  mounted() {
    setInterval(() => {
      this.activeIndex =
        (this.activeIndex + 1) % this.pillars.length;
    }, 3500);
  }
};
</script>

<style scoped>
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(25px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeInUp {
  animation: fadeInUp 1s ease-out forwards;
}
</style>
