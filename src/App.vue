<script setup lang="ts">
import Header from './components/Header.vue'
import HeroSection from './components/HeroSection.vue'
import IntroductionSection from './components/IntroductionSection.vue'
import SystemSection from './components/SystemSection.vue'
import StrategySection from './components/StrategySection.vue'
import Footer from './components/Footer.vue'

// Smooth scroll implementation
const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

// Make scrollToSection available to child components
defineExpose({ scrollToSection })
</script>

<template>
  <div class="app-container">
    <Header @navigate="scrollToSection" />
    <main>
      <HeroSection />
      <IntroductionSection id="introduction" />
      <SystemSection id="system" />
      <StrategySection id="strategy" />
    </main>
    <Footer />
  </div>
</template>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

main {
  flex: 1;
}
</style>