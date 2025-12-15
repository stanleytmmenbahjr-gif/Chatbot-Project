<template>
<section id="courses" class="py-28 px-10 bg-black text-white">

  <h2 class="text-4xl font-bold text-orange-500 mb-14 text-center">
    Courses
  </h2>

  <div 
    class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-10 max-w-7xl mx-auto"
  >
    <div
      v-for="(course, index) in courses"
      :key="index"
      class="p-8 bg-gray-900/60 backdrop-blur-xl rounded-2xl border border-gray-800
             shadow-lg transform transition-all duration-500 hover:-translate-y-3 
             hover:shadow-orange-500/20 hover:border-orange-500/40
             animate-fadeInUp opacity-0"
      :style="{ animationDelay: `${index * 0.15}s` }"
    >
      <h3 class="text-2xl font-semibold mb-4 text-orange-400 transition-all duration-300 hover:text-orange-300">
        {{ course.name }}
      </h3>

      <p class="text-gray-400 mb-6 leading-relaxed">
        {{ course.desc }}
      </p>

      <button
        class="px-5 py-2.5 bg-orange-500 text-black font-bold rounded-lg
               transition-all duration-300 hover:bg-orange-400 hover:scale-105"
      >
        Learn More
      </button>
    </div>
  </div>

</section>
</template>


<script>
export default {
  name: "CoursesSection",

  data() {
    return {
      courses: [
        {
          name: "Web Development",
          desc: "Learn HTML, CSS, JavaScript, Vue, and modern web tools."
        },
        {
          name: "Digital Marketing",
          desc: "Master campaigns, SEO, branding, and analytics."
        },
        {
          name: "Data Science Basics",
          desc: "Foundations of Python, data analysis, and AI."
        },
        {
          name: "UI/UX Design",
          desc: "Design user-friendly interfaces with Figma and Adobe XD."
        },
        {
          name: "Mobile App Development",
          desc: "Build apps for iOS and Android using Flutter."
        },
        {
          name: "Entrepreneurship 101",
          desc: "Start and grow your tech business effectively."
        }

        
      ]
    };
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
    transform: translateY(0px);
  }
}

.animate-fadeInUp {
  animation: fadeInUp 1s ease-out forwards;
}
</style>
