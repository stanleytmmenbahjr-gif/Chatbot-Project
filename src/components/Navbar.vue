<template>
  <header
    class="fixed top-0 left-0 w-full bg-gray-900 shadow-md flex items-center justify-between px-6 py-3 z-50"
  >
    <!-- LOGO + NAME -->
    <div class="flex items-center space-x-3">
      <img :src="logo" class="w-10 h-10 object-contain" />
      <h1 class="text-xl font-bold text-orange-500">
        Orange Digital Center Liberia
      </h1>
    </div>

    <!-- NAV LINKS -->
    <nav class="flex space-x-6 text-gray-700 font-medium">
      <a href="#home" class="hover:text-orange-500">Home</a>
      <a href="#courses" class="hover:text-orange-500">Courses</a>
      <a href="#services" class="hover:text-orange-500">Services</a>
      <a href="#chat" class="hover:text-orange-500">AI Chat</a>
      <a href="#login" class="hover:text-orange-500">Login</a>
    </nav>
  </header>
</template>

<script>
const logo = new URL('../assets/odc-logo.jpg', import.meta.url).href

export default {
  name: "Navbar",
  data() {
    return { logo }
  }
}
</script>

<style>
html {
  scroll-behavior: smooth;
}
</style>
