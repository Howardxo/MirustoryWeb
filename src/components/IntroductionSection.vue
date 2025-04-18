<script setup lang="ts">
defineProps<{
  id?: string
}>()
</script>

<template>
  <section :id="id" class="introduction-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Welcome to the World of MapleStory</h2>
        <p class="section-subtitle">Discover a vibrant and enchanting universe filled with adventure</p>
      </div>
      
      <div class="intro-content">
        <div class="intro-image">
          <img src="https://via.placeholder.com/600x400?text=MapleStory+World" alt="MapleStory World" class="rounded shadow-lg" />
        </div>
        
        <div class="intro-text">
          <h3>A Magical Journey Awaits</h3>
          <p>
            MapleStory is a free-to-play, 2D, side-scrolling MMORPG set in a vibrant fantasy world. Since its launch in 2003, 
            this beloved game has captured the hearts of millions with its charming pixel art, engaging gameplay, and rich storyline.
          </p>
          
          <h3>The Story of Maple World</h3>
          <p>
            Long ago, the peaceful world of Maple was threatened by the Black Mage, a dark wizard with immense power. 
            Five heroes rose to challenge him, but were ultimately defeated and sealed away in ice. 
            Centuries later, you embark on your own adventure in a world still recovering from the Black Mage's influence.
          </p>
          
          <div class="intro-features">
            <div class="feature-item">
              <div class="feature-icon">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="icon">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 10l-2 1m0 0l-2-1m2 1v2.5M20 7l-2 1m2-1l-2-1m2 1v2.5M14 4l-2-1-2 1M4 7l2-1M4 7l2 1M4 7v2.5M12 21l-2-1m2 1l2-1m-2 1v-2.5M6 18l-2-1v-2.5M18 18l2-1v-2.5" />
                </svg>
              </div>
              <div class="feature-content">
                <h4>Vast World</h4>
                <p>Explore diverse continents, each with unique landscapes and challenges</p>
              </div>
            </div>
            
            <div class="feature-item">
              <div class="feature-icon">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="icon">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
                </svg>
              </div>
              <div class="feature-content">
                <h4>Social Experience</h4>
                <p>Join guilds, make friends, and tackle challenges together</p>
              </div>
            </div>
            
            <div class="feature-item">
              <div class="feature-icon">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="icon">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
                </svg>
              </div>
              <div class="feature-content">
                <h4>Constant Evolution</h4>
                <p>Regular updates with new content, classes, and events</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.introduction-section {
  background-color: var(--color-neutral-50);
}

.section-header {
  text-align: center;
  margin-bottom: var(--space-12);
}

.section-title {
  color: var(--color-primary-600);
  margin-bottom: var(--space-4);
}

.section-subtitle {
  font-size: var(--font-size-xl);
  color: var(--color-neutral-600);
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

.intro-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-8);
}

.intro-image img {
  width: 100%;
  height: auto;
  transition: transform var(--transition-normal) var(--transition-function);
}

.intro-image img:hover {
  transform: scale(1.02);
}

.intro-text h3 {
  color: var(--color-secondary-600);
  margin-top: var(--space-6);
  margin-bottom: var(--space-4);
}

.intro-text p {
  margin-bottom: var(--space-6);
  color: var(--color-neutral-700);
  line-height: 1.6;
}

.intro-features {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-6);
  margin-top: var(--space-8);
}

.feature-item {
  display: flex;
  align-items: flex-start;
  gap: var(--space-4);
}

.feature-icon {
  flex-shrink: 0;
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--color-primary-100);
  color: var(--color-primary-600);
  border-radius: var(--radius-full);
}

.icon {
  width: 24px;
  height: 24px;
}

.feature-content h4 {
  margin-bottom: var(--space-2);
  color: var(--color-neutral-800);
}

.feature-content p {
  margin-bottom: 0;
  color: var(--color-neutral-600);
}

@media (min-width: 768px) {
  .intro-content {
    grid-template-columns: 1fr 1fr;
    align-items: center;
  }
  
  .intro-features {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 767px) {
  .intro-content {
    text-align: center;
  }
  
  .feature-item {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
}
</style>