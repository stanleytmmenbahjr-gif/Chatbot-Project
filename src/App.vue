<template>
<div class="min-h-screen bg-black text-white font-sans">
	<Navbar />
	<HeroSection />
	<InfoSection />
	<CoursesSection />

	<!-- Render additional site sections -->
	<EventsSection />
	<ExploreSection />
	<SuccessStories />
	<PartnersSection />

	<LoginSection />
	<ChatFloating />

	<FooterSection />
</div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import HeroSection from './components/HeroSection.vue'
import InfoSection from './components/InfoSection.vue'
import CoursesSection from './components/CoursesSection.vue'
import LoginSection from './components/LoginSection.vue'
import ChatFloating from './components/ChatFloating.vue'
import EventsSection from './components/EventsSection.vue'
import FooterSection from './components/FooterSection.vue'
import ExploreSection from './components/ExploreSection.vue'
import PartnersSection from './components/PartnersSection.vue'
import SuccessStories from './components/SuccessStories.vue'


export default {
	name: 'App',
	components: {
		Navbar,
		HeroSection,
		InfoSection,
		CoursesSection,
		LoginSection,
		ChatFloating,
		EventsSection,
		FooterSection,
		ExploreSection,
		PartnersSection,
		SuccessStories
	}
}
</script>