<template>
  <div class="min-h-screen bg-black text-white font-sans">
    <Navbar @open-login="showLoginModal = true" />

    <HeroSection />
    <InfoSection />
    <ExploreSection />
    <CoursesSection />
    <EventsSection />
    <SuccessStories />
    <PartnersSection />

    <LoginSection v-if="showLoginModal" @close="showLoginModal = false" />

    <ChatFloating />
    <FooterSection />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import HeroSection from './components/HeroSection.vue'
import InfoSection from './components/InfoSection.vue'
import ExploreSection from './components/ExploreSection.vue'
import CoursesSection from './components/CoursesSection.vue'
import EventsSection from './components/EventsSection.vue'
import SuccessStories from './components/SuccessStories.vue'
import PartnersSection from './components/PartnersSection.vue'
import ChatFloating from './components/ChatFloating.vue'
import LoginSection from './components/LoginSection.vue'
import FooterSection from './components/FooterSection.vue'

export default {
  name: 'App',
  data() {
    return {
      showLoginModal: false
    }
  },
  components: {
    Navbar,
    HeroSection,
    InfoSection,
    ExploreSection,
    CoursesSection,
    EventsSection,
    SuccessStories,
    PartnersSection,
    ChatFloating,
    LoginSection,
    FooterSection
  }
}
</script>
