<template>
<section 
  id="welcome"
  class="relative pt-40 pb-32 px-8 text-center bg-black overflow-hidden"
>

  <!-- Background Slideshow Wrapper -->
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

  <!-- Dark overlay for readability -->
  <div class="absolute inset-0 bg-black/65"></div>

  <!-- Content -->
  <div class="relative z-10 max-w-3xl mx-auto text-white animate-fadeInUp">
    <h1 
      class="text-5xl font-bold mb-5 leading-tight tracking-tight drop-shadow-xl
             transition-all duration-700 hover:text-orange-400"
    >
      Welcome to Orange Digital Center Liberia
    </h1>

    <p 
      class="text-gray-300 text-lg mb-10 leading-relaxed opacity-90
             transition-all duration-700 hover:opacity-100"
             
    >
      Building digital skills, empowering young innovators, and accelerating Liberia’s tech future.
    </p>

    <button
      class="px-10 py-4 bg-orange-500 text-black font-bold rounded-xl text-lg
             shadow-lg transition-all duration-500 transform
             hover:bg-orange-400 hover:scale-110 hover:shadow-2xl"
    >
      Explore Programs
    </button>
  </div>

</section>
</template>


<script>
// add as many images as you want here (use URL to handle spaces in filenames)
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
    // auto-change every 6 seconds
    setInterval(() => {
      this.currentImage = (this.currentImage + 1) % this.images.length
    }, 6000)
  }
}
</script>


<style scoped>
/* Fade animation */
.fade-enter-active, .fade-leave-active {
  transition: opacity 1.5s ease-in-out;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}

/* Hero intro animation */
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(25px);
  }
  100% {
    opacity: 1;
    transform: translateY(0px);
  }
}
.animate-fadeInUp {
  animation: fadeInUp 1.1s ease-out forwards;
}
</style>
