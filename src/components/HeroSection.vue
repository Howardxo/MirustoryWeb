<script setup lang="ts">
import { onMounted, ref } from 'vue'

const heroRef = ref<HTMLElement | null>(null)

// Simple particle animation system
const createParticles = () => {
  if (!heroRef.value) return
  
  const heroElement = heroRef.value
  const particleCount = 50
  
  for (let i = 0; i < particleCount; i++) {
    const particle = document.createElement('div')
    particle.classList.add('particle')
    
    // Randomize particle properties
    const size = Math.random() * 10 + 5
    const posX = Math.random() * 100
    const posY = Math.random() * 100
    const duration = Math.random() * 20 + 10
    const delay = Math.random() * 5
    
    particle.style.width = `${size}px`
    particle.style.height = `${size}px`
    particle.style.left = `${posX}%`
    particle.style.top = `${posY}%`
    particle.style.animationDuration = `${duration}s`
    particle.style.animationDelay = `${delay}s`
    
    heroElement.appendChild(particle)
  }
}

onMounted(() => {
  createParticles()
})
</script>

<template>
  <section class="hero-section" ref="heroRef">
    <div class="container">
      <div class="hero-content">
        <h1 class="hero-title">
          Begin Your Epic Adventure in MapleStory
        </h1>
        <p class="hero-subtitle">
          Explore the magical world of Maple, battle fierce monsters, and forge legendary friendships
        </p>
        <div class="hero-cta">
          <a href="#" class="btn btn-primary">Download Now</a>
          <a href="#introduction" class="btn btn-outline">Learn More</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  position: relative;
  height: 100vh;
  min-height: 600px;
  display: flex;
  align-items: center;
  background: linear-gradient(135deg, var(--color-primary-900), var(--color-secondary-900));
  background-size: cover;
  background-position: center;
  color: white;
  overflow: hidden;
}

.hero-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('https://images.unsplash.com/photo-1518709268805-4e9042af9f23?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80');
  background-size: cover;
  background-position: center;
  opacity: 0.4;
  z-index: 1;
}

.hero-content {
  position: relative;
  z-index: 2;
  max-width: 800px;
  text-align: center;
  margin: 0 auto;
  padding: var(--space-8);
}

.hero-title {
  font-size: clamp(var(--font-size-3xl), 5vw, var(--font-size-6xl));
  margin-bottom: var(--space-6);
  color: white;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
  animation: fadeInUp 1s ease-out;
}

.hero-subtitle {
  font-size: clamp(var(--font-size-lg), 2vw, var(--font-size-2xl));
  margin-bottom: var(--space-8);
  color: var(--color-neutral-100);
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
  animation: fadeInUp 1s ease-out 0.2s both;
}

.hero-cta {
  display: flex;
  gap: var(--space-4);
  justify-content: center;
  animation: fadeInUp 1s ease-out 0.4s both;
}

@media (max-width: 640px) {
  .hero-cta {
    flex-direction: column;
    gap: var(--space-4);
    width: 100%;
  }
  
  .hero-cta .btn {
    width: 100%;
  }
}

/* Particles */
.particle {
  position: absolute;
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  pointer-events: none;
  opacity: 0;
  animation: float infinite linear both;
}

@keyframes float {
  0% {
    transform: translateY(0) rotate(0deg);
    opacity: 0;
  }
  10% {
    opacity: 0.5;
  }
  90% {
    opacity: 0.5;
  }
  100% {
    transform: translateY(-100vh) rotate(360deg);
    opacity: 0;
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>