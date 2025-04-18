<script setup lang="ts">
import { onMounted, ref } from 'vue'

const heroRef = ref<HTMLElement | null>(null)

// 粒子動畫系統（保持不變）
const createParticles = () => {
  if (!heroRef.value) return

  const heroElement = heroRef.value
  const particleCount = 50

  for (let i = 0; i < particleCount; i++) {
    const particle = document.createElement('div')
    particle.classList.add('particle')

    // 隨機化粒子屬性
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
  <div class="header-spacer"></div>
  <section class="hero-section" ref="heroRef">
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
  </section>
</template>

<style scoped>
.header-spacer {
  height: 80px;
}

.hero-section {
  position: relative;
  height: calc(100vh - 80px);
  min-height: calc(600px - 80px);
  width: 100vw;
  margin-top: -80px;
  padding-top: 80px;
  display: grid;
  place-items: center;
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
  background-image: url('https://images.unsplash.com/photo-1518709268805-4e9042af9f23?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
  background-size: cover;
  background-position: center;
  opacity: 0.4;
  z-index: 1;
}

.hero-content {
  position: relative;
  z-index: 3;
  width: min(90vw, 800px);
  margin: 0 auto;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  transform: translateY(5%);
  padding: 2rem 0;
}

/* 保持原有 hero-title、hero-subtitle、hero-cta 樣式 */

@media (max-width: 768px) {
  .header-spacer {
    height: 60px;
  }
  .hero-section {
    height: calc(100vh - 60px);
    min-height: calc(600px - 60px);
    margin-top: -60px;
    padding-top: 60px;
  }
  .hero-content {
    transform: translateY(0);
  }
}

.particle {
  position: absolute;
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  pointer-events: none;
  opacity: 0;
  z-index: 2;
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
