<template>
  <section id="explore" class="py-28 px-6 md:px-14 bg-black relative overflow-hidden">
    
    <!-- subtle background glow -->
    <div class="absolute -top-32 left-1/2 -translate-x-1/2 w-[600px] h-[600px] bg-orange-500/10 blur-[120px]"></div>

    <h2 class="text-4xl md:text-5xl font-bold text-orange-500 mb-14 text-center tracking-tight">
      Explore Orange Digital Center
    </h2>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-12 relative z-10">

      <!-- Card -->
      <div
        v-for="(card, i) in cards"
        :key="i"
        class="group relative rounded-2xl overflow-hidden bg-gray-900 border border-gray-800
               transition-all duration-700 hover:-translate-y-3 hover:shadow-2xl hover:shadow-orange-500/20"
      >
        <!-- Image -->
        <div class="relative h-56 overflow-hidden">
          <img
            :src="card.img"
            :alt="card.title"
            class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110"
          />

          <!-- dark gradient -->
          <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/30 to-transparent"></div>

          <!-- hover overlay -->
          <div
            class="absolute inset-0 flex flex-col justify-end p-6
                   bg-gradient-to-t from-orange-500/90 via-orange-500/40 to-transparent
                   opacity-0 group-hover:opacity-100 transition-opacity duration-700"
          >
            <h3 class="text-2xl font-bold text-white mb-2">
              {{ card.title }}
            </h3>
            <p class="text-sm text-white-bold/90 leading-relaxed">
              {{ card.desc }}
            </p>
          </div>
        </div>

        <!-- Footer -->
        <div class="p-6">
          <button
            class="w-full py-3 rounded-lg font-semibold tracking-wide
                   bg-transparent text-orange-500 border border-orange-500/60
                   transition-all duration-500
                   hover:bg-orange-500 hover:text-black hover:shadow-lg hover:shadow-orange-500/30"
          >
            {{ card.btn }}
          </button>
        </div>
      </div>

    </div>
  </section>
</template>

<script>
const img1 = new URL('../assets/coding.jpg', import.meta.url).href
const img2 = new URL('../assets/fab.jpg', import.meta.url).href
const img3 = new URL('../assets/Startup.jpg', import.meta.url).href

export default {
  name: 'ExploreSection',
  data() {
    return {
      cards: [
        {
          title: 'Coding School',
          desc: 'A modern environment for software engineering, problem-solving, and digital mastery.',
          btn: 'Learn More',
          img: img1
        },
        {
          title: 'Fab Lab',
          desc: 'A creative fabrication space for prototyping, hardware innovation, and experimentation.',
          btn: 'Explore',
          img: img2
        },
        {
          title: 'Startup Incubator',
          desc: 'Mentorship, tools, and support for founders turning ideas into scalable ventures.',
          btn: 'View Details',
          img: img3
        }
      ]
    }
  }
}
</script>
