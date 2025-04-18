<script setup lang="ts">
defineProps<{
  id?: string
}>()

// Strategy tips data
const strategyTips = [
  {
    title: 'Leveling Efficiently',
    description: 'Focus on completing main quests and hunting monsters that match your level for maximum experience gain.',
    icon: 'M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z'
  },
  {
    title: 'Managing Resources',
    description: 'Save mesos for essential purchases and use consumables wisely during challenging battles.',
    icon: 'M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z'
  },
  {
    title: 'Building Your Character',
    description: 'Plan your skill point allocation carefully and invest in gear that complements your class.',
    icon: 'M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2'
  },
  {
    title: 'Party Play',
    description: 'Team up with other players for challenging dungeons and boss fights for greater rewards.',
    icon: 'M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z'
  },
  {
    title: 'Boss Strategies',
    description: 'Learn boss mechanics and patterns to avoid deadly attacks and maximize damage opportunities.',
    icon: 'M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z'
  },
  {
    title: 'Daily Routines',
    description: 'Complete daily quests and participate in time-limited events for valuable rewards.',
    icon: 'M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z'
  }
]

// FAQ data
const faqs = [
  {
    question: 'What class should I start with?',
    answer: 'If you\'re new to MapleStory, we recommend starting with Explorer classes like Warrior, Magician, or Bowman as they offer balanced gameplay and are easier to master. Adventurer classes provide a good foundation for understanding the game mechanics.'
  },
  {
    question: 'How do I earn mesos quickly?',
    answer: 'The most reliable ways to earn mesos include daily bosses, selling valuable items on the Auction House, completing Ursus during 2x meso time, and farming in maps with high meso drop rates. Using a Wealth Acquisition Potion and equipping items with meso obtain rate can significantly boost your earnings.'
  },
  {
    question: 'What should I focus on as a new player?',
    answer: 'As a new player, focus on leveling up through the main storyline quests, unlocking essential systems like the Maple Guide and Link Skills, and gradually building your equipment set. Don\'t worry too much about optimization initially - enjoy exploring the world and understanding the basic mechanics.'
  },
  {
    question: 'How important are link skills?',
    answer: 'Link Skills are extremely important for long-term progression. They allow you to share beneficial abilities between characters on your account. Building up several characters to level 120-210 will provide substantial bonuses that make your main character significantly stronger. Consider this a long-term goal to work towards.'
  }
]
</script>

<template>
  <section :id="id" class="strategy-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Strategy Guide</h2>
        <p class="section-subtitle">Master the game with these essential tips and tricks</p>
      </div>
      
      <div class="strategy-content">
        <div class="strategy-tips">
          <h3>Pro Tips for Success</h3>
          
          <div class="tips-grid">
            <div v-for="tip in strategyTips" :key="tip.title" class="tip-card card">
              <div class="tip-icon">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" :d="tip.icon" />
                </svg>
              </div>
              <div class="tip-content">
                <h4>{{ tip.title }}</h4>
                <p>{{ tip.description }}</p>
              </div>
            </div>
          </div>
        </div>
        
        <div class="strategy-faq">
          <h3>Frequently Asked Questions</h3>
          
          <div class="faq-list">
            <div v-for="(faq, index) in faqs" :key="index" class="faq-item">
              <div class="faq-question">
                <h4>{{ faq.question }}</h4>
              </div>
              <div class="faq-answer">
                <p>{{ faq.answer }}</p>
              </div>
            </div>
          </div>
          
          <div class="strategy-cta">
            <h3>Ready to Begin Your Adventure?</h3>
            <p>Join millions of players in the magical world of MapleStory!</p>
            <a href="#" class="btn btn-primary">Download Now</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.strategy-section {
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

.strategy-content {
  display: flex;
  flex-direction: column;
  gap: var(--space-16);
}

.strategy-tips h3,
.strategy-faq h3 {
  text-align: center;
  color: var(--color-secondary-600);
  margin-bottom: var(--space-8);
}

.tips-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: var(--space-6);
}

.tip-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: var(--space-6);
}

.tip-icon {
  width: 60px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--color-primary-100);
  color: var(--color-primary-600);
  border-radius: var(--radius-full);
  margin-bottom: var(--space-4);
}

.tip-icon svg {
  width: 32px;
  height: 32px;
}

.tip-content h4 {
  color: var(--color-primary-600);
  margin-bottom: var(--space-2);
}

.tip-content p {
  color: var(--color-neutral-700);
}

.faq-list {
  display: flex;
  flex-direction: column;
  gap: var(--space-4);
}

.faq-item {
  background-color: white;
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-md);
  overflow: hidden;
  transition: all var(--transition-normal) var(--transition-function);
}

.faq-item:hover {
  box-shadow: var(--shadow-lg);
}

.faq-question {
  padding: var(--space-4) var(--space-6);
  background-color: var(--color-primary-50);
  border-bottom: 1px solid var(--color-primary-100);
}

.faq-question h4 {
  color: var(--color-primary-700);
  margin: 0;
}

.faq-answer {
  padding: var(--space-4) var(--space-6);
}

.faq-answer p {
  color: var(--color-neutral-700);
  margin: 0;
}

.strategy-cta {
  margin-top: var(--space-12);
  text-align: center;
  padding: var(--space-8);
  background-color: white;
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-lg);
}

.strategy-cta h3 {
  color: var(--color-primary-600);
  margin-bottom: var(--space-4);
}

.strategy-cta p {
  color: var(--color-neutral-700);
  margin-bottom: var(--space-6);
  font-size: var(--font-size-lg);
}

@media (min-width: 640px) {
  .tips-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 768px) {
  .tip-card {
    flex-direction: row;
    text-align: left;
    align-items: flex-start;
  }
  
  .tip-icon {
    margin-right: var(--space-4);
    margin-bottom: 0;
  }
}

@media (min-width: 1024px) {
  .tips-grid {
    grid-template-columns: repeat(3, 1fr);
  }
  
  .tip-card {
    flex-direction: column;
    text-align: center;
    align-items: center;
  }
  
  .tip-icon {
    margin-right: 0;
    margin-bottom: var(--space-4);
  }
}
</style>