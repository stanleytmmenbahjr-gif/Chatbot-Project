<template>
  <div class="fixed bottom-6 right-6 z-50">

    <!-- Chat Panel -->
    <div
      v-if="open"
      class="mb-4 w-80 bg-gray-900 border border-gray-800
             rounded-2xl shadow-2xl p-5 text-white animate-slideUp"
    >
      <p class="text-sm text-gray-300 mb-4">
        Hello welcome to our support center if you need any assitans
        click on our Representative below to Chat
      </p>

      <!-- Representative -->
      <a
        :href="messengerLink"
        target="_blank"
        rel="noopener"
        class="flex items-center gap-4 p-3 rounded-xl
               hover:bg-gray-800 transition"
      >
        

        <div>
          <p class="text-sm text-orange-400 font-semibold">
            Technical Support
          </p>
          <p class="text-base font-bold">
            Stanley T M Menbah Jr 
          </p>
          <p class="text-xs text-gray-400">
            Opening hours: 8am – 6pm
          </p>
        </div>
      </a>
    </div>

    <!-- Floating Button -->
    <button
      @click="toggle"
      class="w-16 h-16 rounded-full flex items-center justify-center
             shadow-2xl bg-gradient-to-br from-orange-500 to-yellow-400
             hover:scale-110 transition-transform duration-300"
    >
      <svg
        v-if="!open"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        fill="currentColor"
        class="w-8 h-8 text-black"
      >
        <path
          d="M12 2C6.48 2 2 6.14 2 11.25c0 2.91 1.41 5.49 3.61 7.21V22l3.32-1.82c.98.27 2.02.42 3.07.42 5.52 0 10-4.14 10-9.25S17.52 2 12 2z"
        />
      </svg>

      <span v-else class="text-black text-2xl font-bold">
        ×
      </span>
    </button>

  </div>
</template>

<script>
export default {
  name: "ChatFloating",
  data() {
    return {
      open: false
    }
  },
  mounted() {
    this._openChatHandler = () => { this.open = true }
    window.addEventListener('open-chat', this._openChatHandler)
  },
  unmounted() {
    window.removeEventListener('open-chat', this._openChatHandler)
  },
  computed: {
    messengerLink() {
      return "https://m.me/Stanley.T.M.Menbah.Jr"
      // fallback:
      // return "https://m.me/889130790124735"
    }
  },
  methods: {
    toggle() {
      this.open = !this.open
    }
  }
}
</script>

<style scoped>
@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(15px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-slideUp {
  animation: slideUp 0.25s ease-out forwards;
}
</style>
