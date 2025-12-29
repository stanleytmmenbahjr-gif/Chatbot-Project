<template>
  <header class="fixed top-0 left-0 w-full bg-gray-900 shadow-md z-50">
    <div class="flex items-center justify-between px-6 py-3">
      <div class="flex items-center gap-3">
        <img :src="logo" class="w-10 h-10" />
        <h1 class="text-lg font-bold text-orange-500">
          Orange Digital Center
        </h1>
      </div>

      <nav class="hidden md:flex gap-6 text-gray-300 items-center">
        <a href="#home" class="hover:text-orange-500">Home</a>
        <a href="#explore" class="hover:text-orange-500">Explore</a>
        <a href="#courses" class="hover:text-orange-500">Courses</a>
        <a href="#events" class="hover:text-orange-500">Events</a>
        <a href="#Partners" class="hover:text-orange-500">Partners</a>
        <a href="#SuccessStories" class="hover:text-orange-500">SuccessStories</a>
        <a href="#chat" class="hover:text-orange-500">AI Chat</a>
        <button @click="$emit('open-login')" class="px-4 py-2 bg-orange-500 text-black font-bold rounded hover:bg-orange-600">Login</button>
      </nav>

      <button class="md:hidden text-3xl text-orange-500" @click="menuOpen = !menuOpen">
        ☰
      </button>
    </div>

    <div v-if="menuOpen" class="md:hidden bg-gray-950 px-6 py-6 space-y-4">
      <a @click="close" href="#home" class="block">Home</a>
      <a @click="close" href="#explore" class="block">Explore</a>
      <a @click="close" href="#courses" class="block">Courses</a>
      <a @click="close" href="#events" class="block">Events</a>
      <a @click="close" href="#chat" class="block">AI Chat</a>
    </div>
  </header>
</template>

<script>
const logo = new URL('../assets/odc-logo.jpg', import.meta.url).href
export default {
  data() {
    return { logo, menuOpen: false }
  },
  methods: {
    close() {
      this.menuOpen = false
    }
  }
}
</script>

<style>
html { scroll-behavior: smooth; }
</style>
