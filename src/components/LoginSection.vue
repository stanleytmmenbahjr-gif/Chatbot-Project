<template>
<div class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
  <section id="auth" class="w-full max-w-md bg-gray-950 text-white rounded-xl p-8 relative">
    <!-- Close Button -->
    <button @click="$emit('close')" class="absolute top-4 right-4 text-2xl text-gray-400 hover:text-white">
      ×
    </button>

    <div class="flex items-center justify-center mb-6">
      <img :src="logo" alt="ODC Logo" class="w-12 h-12 mr-3" />
      <h1 class="text-2xl font-bold text-orange-500">Orange Digital Center</h1>
    </div>

    <h2 class="text-3xl font-bold text-orange-500 mb-8 text-center">
      {{ isFirstTime ? "Create Your Account" : isLoginMode ? "Login" : "Create Your Account" }}
    </h2>

    <!-- NAME for signup only -->
    <input 
      v-if="!isLoginMode"
      v-model="name"
      type="text"
      placeholder="Full Name" 
      class="w-full mb-4 p-3 bg-black border border-gray-700 rounded" 
    />

    <input 
      v-model="email"
      type="text" 
      placeholder="Email" 
      class="w-full mb-4 p-3 bg-black border border-gray-700 rounded" 
    />

    <input 
      v-model="password"
      type="password" 
      placeholder="Password" 
      class="w-full mb-4 p-3 bg-black border border-gray-700 rounded"
    />

    <!-- Remember Me (only in login mode) -->
    <div v-if="isLoginMode" class="flex items-center mb-4">
      <input 
        type="checkbox" 
        id="remember" 
        v-model="rememberMe"
        class="mr-2"
      />
      <label for="remember">Remember Me</label>
    </div>

    <!-- Button -->
    <button 
      class="w-full py-3 bg-orange-500 text-black font-bold rounded mb-4"
      @click="handleAuth"
    >
      {{ isLoginMode ? "Sign In" : "Sign Up" }}
    </button>

    <!-- Switch Modes -->
    <p class="text-gray-400 text-sm cursor-pointer text-center"
       @click="toggleMode">
      {{ isLoginMode ? "Don't have an account? Sign up" : "Already have an account? Login" }}
    </p>
  </section>
</div>
</template>


<script>
const logo = new URL('../assets/odc-logo.jpg', import.meta.url).href

export default {
  name: "LoginSignup",

  data() {
    return {
      logo,
      isLoginMode: true,
      name: "",
      email: "",
      password: "",
      rememberMe: false,
      isFirstTime: false
    };
  },

  mounted() {
    // Detect if first time
    const user = localStorage.getItem("odcUser");
    if (!user) {
      this.isLoginMode = false;
      this.isFirstTime = true;
    } else {
      this.isLoginMode = true;
      this.isFirstTime = false;
    }

    // Auto-fill if rememberMe was set
    const saved = JSON.parse(localStorage.getItem("odcRememberMe"));
    if (saved) {
      this.email = saved.email;
      this.password = saved.password;
      this.rememberMe = true;
    }
  },

  methods: {
    handleAuth() {
      if (this.isLoginMode) {
        // LOGIN
        const user = JSON.parse(localStorage.getItem("odcUser"));

        if (!user) {
          alert("No account found. Please sign up first.");
          this.isLoginMode = false;
          return;
        }

        if (user.email === this.email && user.password === this.password) {
          if (this.rememberMe) {
            localStorage.setItem("odcRememberMe", JSON.stringify({
              email: this.email,
              password: this.password
            }));
          } else {
            localStorage.removeItem("odcRememberMe");
          }

          alert("Login successful.");
        } else {
          alert("Invalid email or password.");
        }
        
      } else {
        // SIGNUP
        if (!this.name || !this.email || !this.password) {
          alert("Please fill all fields.");
          return;
        }

        const newUser = {
          name: this.name,
          email: this.email,
          password: this.password
        };

        localStorage.setItem("odcUser", JSON.stringify(newUser));
        alert("Signup successful! Please log in.");

        // Switch to login mode
        this.isLoginMode = true;
      }
    },

    toggleMode() {
      this.isLoginMode = !this.isLoginMode;
    }
  }
};
</script>
