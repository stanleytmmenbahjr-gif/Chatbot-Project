<template>
  <div>
    <!-- Floating Robot Button -->
    <button 
      @click="opened = !opened" 
      class="fixed bottom-6 right-6 w-16 h-16 rounded-full flex items-center justify-center shadow-2xl bg-gradient-to-br from-orange-500 to-yellow-400 hover:scale-110 transition-transform duration-300"
    >
      <svg xmlns="src/assests/Robort.jpg" class="w-8 h-8 text-black" fill="currentColor" viewBox="0 0 24 24">
        <path d="M12 2a2 2 0 0 0-2 2v2h4V4a2 2 0 0 0-2-2zm8 6h-2v6h2V8zm-16 0H2v6h2V8zm14 10a2 2 0 0 1-2 2H8a2 2 0 0 1-2-2v-4h12v4zm-6-7a1 1 0 1 1 0-2 1 1 0 0 1 0 2zm-4 0a1 1 0 1 1 0-2 1 1 0 0 1 0 2z"/>
      </svg>
    </button>

    <!-- Chat Window -->
    <div 
      v-if="opened" 
      class="fixed bottom-24 right-6 w-80 bg-gradient-to-t from-gray-900 to-gray-800 border border-gray-700 rounded-2xl p-4 shadow-xl transform scale-95 animate-fadeIn"
      style="max-height: 60vh;"
    >
      <!-- Messages Area -->
      <div class="overflow-y-auto space-y-3 mb-3 scrollbar-thin scrollbar-thumb-orange-500 scrollbar-track-gray-700 p-2 rounded" style="max-height: calc(60vh - 60px);">
        <div class="bg-gradient-to-r from-orange-500 to-yellow-400 text-black p-3 rounded-xl shadow-md animate-pulse">
          Hello! Ask me anything about ODC Liberia.
        </div>
        <div v-if="response" class="bg-gray-700 text-white p-3 rounded-xl shadow-md animate-slideIn">
          {{ response }}
        </div>
      </div>

      <!-- Input -->
      <input
        v-model="text"
        @keyup.enter="sendMessage"
        placeholder="Type message..."
        class="w-full p-2 bg-black border border-gray-700 rounded-xl text-white focus:outline-none focus:ring-2 focus:ring-orange-500"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatFloating',
  data() {
    return {
      opened: false,
      text: '',
      response: ''
    }
  },
  methods: {
    sendMessage() {
      if (!this.text.trim()) return;
      this.response = `You asked: "${this.text}". Here’s a magical reply! ✨`;
      this.text = '';
      this.$nextTick(() => {
        const container = this.$el.querySelector('div.overflow-y-auto');
        container.scrollTop = container.scrollHeight;
      });
    }
  }
}
</script>

<style scoped>
@keyframes fadeIn {
  from {opacity: 0; transform: translateY(20px);}
  to {opacity: 1; transform: translateY(0);}
}
.animate-fadeIn { animation: fadeIn 0.3s ease-out forwards; }

@keyframes slideIn {
  from {opacity: 0; transform: translateX(-30px);}
  to {opacity: 1; transform: translateX(0);}
}
.animate-slideIn { animation: slideIn 0.4s ease-out forwards; }

.scrollbar-thin { scrollbar-width: thin; }
.scrollbar-thumb-orange-500::-webkit-scrollbar-thumb { background-color: #f97316; border-radius: 8px; }
.scrollbar-track-gray-700::-webkit-scrollbar-track { background-color: #374151; border-radius: 8px; }
.scrollbar-thumb-orange-500::-webkit-scrollbar { width: 6px; }
</style>
