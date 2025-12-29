<template>
  <section
    id="welcome"
    class="relative pt-28 sm:pt-36 md:pt-44 pb-24 sm:pb-32
           px-6 sm:px-8 text-center bg-black overflow-hidden"
  >

    <!-- Background Slideshow -->
    <div class="absolute inset-0 overflow-hidden">
      <transition-group name="fade" tag="div">
        <div
          v-for="(image, index) in images"
          :key="index"
          v-show="currentImage === index"
          class="absolute inset-0 bg-cover bg-center"
          :style="{ backgroundImage: `url(${image})` }"
        ></div>
      </transition-group>
    </div>

    <!-- Dark Overlay -->
    <div class="absolute inset-0 bg-black/70"></div>

    <!-- Content -->
    <div class="relative z-10 max-w-3xl mx-auto text-white animate-fadeInUp">

      <h1
        class="text-3xl sm:text-4xl md:text-5xl
               font-bold mb-4 sm:mb-5
               leading-tight tracking-tight drop-shadow-xl
               transition-colors duration-500 hover:text-orange-400"
      >
        Welcome to Orange Digital Center Liberia
      </h1>

      <p
        class="text-gray-300 text-base sm:text-lg
               mb-8 sm:mb-10
               leading-relaxed opacity-90"
      >
        Building digital skills, empowering young innovators, and accelerating
        Liberia’s tech future.
      </p>

      <a href="#explore"
   class="inline-block px-6 py-3 sm:px-8 sm:py-4
          bg-orange-500 text-black font-bold text-base sm:text-lg
          rounded-lg sm:rounded-xl shadow-lg
          transition-all duration-500 hover:bg-orange-400 hover:scale-105 hover:shadow-2xl">
  Explore Programs
</a>


    </div>
  </section>
</template>

<script>
const img1 = new URL('../assets/bg.jpg', import.meta.url).href
const img2 = new URL('../assets/bg 2.png', import.meta.url).href
const img3 = new URL('../assets/image.png', import.meta.url).href
const img4 = new URL('../assets/bg 3.jpg', import.meta.url).href
const img5 = new URL('../assets/bg 4.jpg', import.meta.url).href

export default {
  name: "HeroSection",
  data() {
    return {
      images: [img1, img2, img3, img4, img5],
      currentImage: 0
    }
  },
  mounted() {
    setInterval(() => {
      this.currentImage = (this.currentImage + 1) % this.images.length
    }, 6000)
  }
}
</script>

<style scoped>
/* Background fade */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 1.5s ease-in-out;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Content intro */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(24px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeInUp {
  animation: fadeInUp 1s ease-out forwards;
}
</style>
