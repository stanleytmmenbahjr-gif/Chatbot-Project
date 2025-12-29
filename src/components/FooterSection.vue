<template>
<footer class="bg-black border-t border-gray-800 mt-28">

  <!-- main footer -->
  <div class="max-w-7xl mx-auto px-8 py-20 grid grid-cols-1 md:grid-cols-4 gap-14">

    <!-- About + Socials -->
    <div>
      <h3 class="text-orange-500 font-bold text-lg mb-4">
        Orange Digital Center
      </h3>

      <p class="text-gray-400 text-sm leading-relaxed mb-6">
        Empowering Liberia through digital skills, innovation, and future-ready
        technology leadership.
      </p>

      <p class="text-gray-400 text-sm mb-4">Follow us</p>

      <div class="flex items-center gap-4">
        <!-- Facebook -->
        <a
          href="https://www.facebook.com/share/p/181uDkoYXA/"
          aria-label="Facebook"
          class="w-10 h-10 rounded-full border border-gray-700 flex items-center justify-center
                 text-orange-500 transition
                 hover:bg-orange-500 hover:text-black hover:shadow-lg hover:shadow-orange-500/30"
        >
          <svg class="w-5 h-5 fill-current" viewBox="0 0 24 24">
            <path d="M22.675 0h-21.35C.597 0 0 .597 0 1.326v21.348C0 23.403.597 24 1.326 24h11.495v-9.294H9.691V11.01h3.13V8.309c0-3.1 1.893-4.788 4.659-4.788 1.325 0 2.464.099 2.795.143v3.24l-1.918.001c-1.504 0-1.795.715-1.795 1.763v2.312h3.587l-.467 3.696h-3.12V24h6.116C23.403 24 24 23.403 24 22.674V1.326C24 .597 23.403 0 22.675 0z"/>
          </svg>
        </a>

        <!-- X -->
        <a
          href="#"
          aria-label="X"
          class="w-10 h-10 rounded-full border border-gray-700 flex items-center justify-center
                 text-orange-500 transition
                 hover:bg-orange-500 hover:text-black hover:shadow-lg hover:shadow-orange-500/30"
        >
          <svg class="w-5 h-5 fill-current" viewBox="0 0 24 24">
            <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817-5.965 6.817H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231 5.451-6.231z"/>
          </svg>
        </a>

        <!-- Instagram -->
        <a
          href="#"
          aria-label="Instagram"
          class="w-10 h-10 rounded-full border border-gray-700 flex items-center justify-center
                 text-orange-500 transition
                 hover:bg-orange-500 hover:text-black hover:shadow-lg hover:shadow-orange-500/30"
        >
          <svg class="w-5 h-5 fill-current" viewBox="0 0 24 24">
            <path d="M12 2.163c3.204 0 3.584.012 4.85.07 1.366.062 2.633.343 3.608 1.319.975.975 1.257 2.242 1.319 3.608.058 1.266.069 1.645.069 4.84 0 3.204-.012 3.584-.069 4.85-.062 1.366-.344 2.633-1.319 3.608-.975.975-2.242 1.257-3.608 1.319-1.266.057-1.645.069-4.85.069-3.195 0-3.574-.012-4.84-.069-1.366-.062-2.633-.344-3.608-1.319-.976-.975-1.257-2.242-1.319-3.608C2.175 15.584 2.163 15.204 2.163 12c0-3.195.012-3.574.069-4.84.062-1.366.344-2.633 1.319-3.608.975-.976 2.242-1.257 3.608-1.319C8.426 2.175 8.806 2.163 12 2.163z"/>
          </svg>
        </a>
      </div>
    </div>

    <!-- Explore -->
    <div>
      <h3 class="text-orange-500 font-bold mb-4">Explore</h3>
      <ul class="space-y-3 text-sm">
        <li class="text-gray-400 hover:text-orange-400 transition cursor-pointer">Programs</li>
        <li class="text-gray-400 hover:text-orange-400 transition cursor-pointer">Courses</li>
        <li class="text-gray-400 hover:text-orange-400 transition cursor-pointer">Fab Lab</li>
        <li class="text-gray-400 hover:text-orange-400 transition cursor-pointer">Incubation</li>
      </ul>
    </div>

    <!-- Support -->
    <div>
      <h3 class="text-orange-500 font-bold mb-4">Support</h3>
      <ul class="space-y-3 text-sm">
        <li class="text-gray-400 hover:text-orange-400 transition cursor-pointer">FAQs</li>
        <li class="text-gray-400 hover:text-orange-400 transition cursor-pointer">Help Center</li>
        <li class="text-gray-400 hover:text-orange-400 transition cursor-pointer">Contact</li>
      </ul>
    </div>

    <!-- Contact -->
    <div>
      <h3 class="text-orange-500 font-bold mb-4">Contact</h3>
      <p class="text-gray-400 text-sm leading-relaxed">
        Monrovia, Liberia<br />
        <span class="text-orange-400">info@odcliberia.org</span>
      </p>
    </div>

  </div>

  <!-- bottom bar -->
  <div class="border-t border-gray-800 py-6 text-center text-sm text-gray-500" translate="yes">
    © 2025 Orange Digital Center Liberia. All rights reserved. design by <a href="https://web.facebook.com/stanleytmmenbahjr">Stanley T M Menbah Jr</a>
  </div>

</footer>
</template>

<script>
export default {
  name: 'FooterSection'
}
</script>
