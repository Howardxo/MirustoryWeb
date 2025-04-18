<script setup lang="ts">
import { ref } from 'vue'

defineProps<{
  id?: string
}>()

const tabs = ref([
  { id: 'classes', label: 'Classes', active: true },
  { id: 'skills', label: 'Skills', active: false },
  { id: 'equipment', label: 'Equipment', active: false },
  { id: 'progression', label: 'Progression', active: false }
])

const setActiveTab = (tabId: string) => {
  tabs.value = tabs.value.map(tab => ({
    ...tab,
    active: tab.id === tabId
  }))
}

// Class data
const classes = [
  {
    name: 'Warrior',
    description: 'Masters of defense and close combat, Warriors excel at soaking damage and protecting allies.',
    image: 'https://via.placeholder.com/150?text=Warrior',
    stats: { strength: 90, dexterity: 40, intelligence: 30, luck: 40 }
  },
  {
    name: 'Magician',
    description: 'Wielders of arcane might, Magicians cast powerful spells to damage enemies from a distance.',
    image: 'https://via.placeholder.com/150?text=Magician',
    stats: { strength: 30, dexterity: 40, intelligence: 90, luck: 40 }
  },
  {
    name: 'Archer',
    description: 'Masters of precision and ranged combat, Archers excel at taking down targets from afar.',
    image: 'https://via.placeholder.com/150?text=Archer',
    stats: { strength: 40, dexterity: 90, intelligence: 30, luck: 40 }
  },
  {
    name: 'Thief',
    description: 'Agile and cunning, Thieves strike quickly and disappear into the shadows.',
    image: 'https://via.placeholder.com/150?text=Thief',
    stats: { strength: 40, dexterity: 70, intelligence: 30, luck: 60 }
  }
]
</script>

<template>
  <section :id="id" class="system-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Game Systems</h2>
        <p class="section-subtitle">Discover the mechanics that make MapleStory unique and engaging</p>
      </div>
      
      <div class="tabs-container">
        <div class="tabs-header">
          <button 
            v-for="tab in tabs" 
            :key="tab.id"
            :class="['tab-button', { active: tab.active }]"
            @click="setActiveTab(tab.id)"
          >
            {{ tab.label }}
          </button>
        </div>
        
        <div class="tabs-content">
          <!-- Classes Tab -->
          <div v-if="tabs.find(t => t.id === 'classes')?.active" class="tab-pane">
            <div class="classes-grid">
              <div v-for="classItem in classes" :key="classItem.name" class="class-card card">
                <div class="class-image">
                  <img :src="classItem.image" :alt="classItem.name" />
                </div>
                <div class="class-info">
                  <h3>{{ classItem.name }}</h3>
                  <p>{{ classItem.description }}</p>
                  <div class="class-stats">
                    <div class="stat-item">
                      <span class="stat-label">STR</span>
                      <div class="stat-bar">
                        <div 
                          class="stat-fill"
                          :style="{ width: `${classItem.stats.strength}%` }"
                        ></div>
                      </div>
                    </div>
                    <div class="stat-item">
                      <span class="stat-label">DEX</span>
                      <div class="stat-bar">
                        <div 
                          class="stat-fill"
                          :style="{ width: `${classItem.stats.dexterity}%` }"
                        ></div>
                      </div>
                    </div>
                    <div class="stat-item">
                      <span class="stat-label">INT</span>
                      <div class="stat-bar">
                        <div 
                          class="stat-fill"
                          :style="{ width: `${classItem.stats.intelligence}%` }"
                        ></div>
                      </div>
                    </div>
                    <div class="stat-item">
                      <span class="stat-label">LUK</span>
                      <div class="stat-bar">
                        <div 
                          class="stat-fill"
                          :style="{ width: `${classItem.stats.luck}%` }"
                        ></div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Skills Tab -->
          <div v-if="tabs.find(t => t.id === 'skills')?.active" class="tab-pane">
            <div class="skills-content">
              <div class="skills-image">
                <img src="https://via.placeholder.com/600x400?text=Skills+Tree" alt="Skills System" class="rounded shadow-lg" />
              </div>
              <div class="skills-text">
                <h3>Master Your Abilities</h3>
                <p>
                  In MapleStory, your character's growth is defined by the skills you choose to develop. 
                  Each class has unique active and passive abilities that can be customized to fit your playstyle.
                </p>
                
                <h4>Skill Points System</h4>
                <p>
                  As you level up, you'll earn skill points that can be invested into various abilities. 
                  Choose wisely, as your skill distribution will define your character's strengths and weaknesses.
                </p>
                
                <h4>Skill Trees</h4>
                <p>
                  Skills are organized in progressive trees, with more powerful abilities unlocking as you advance. 
                  Some abilities require prerequisites, creating meaningful choices in how you develop your character.
                </p>
                
                <h4>Skill Levels</h4>
                <p>
                  Each skill can be leveled up multiple times, increasing its effectiveness. 
                  Max out your favorite abilities or distribute points more evenly for versatility.
                </p>
              </div>
            </div>
          </div>
          
          <!-- Equipment Tab -->
          <div v-if="tabs.find(t => t.id === 'equipment')?.active" class="tab-pane">
            <div class="equipment-content">
              <div class="equipment-text">
                <h3>Gear Up For Adventure</h3>
                <p>
                  Your equipment plays a crucial role in your character's power. Collect and enhance weapons, armor, 
                  and accessories to boost your stats and unlock special abilities.
                </p>
                
                <div class="equipment-features">
                  <div class="equipment-feature">
                    <h4>Gear Sets</h4>
                    <p>
                      Collect complete sets of equipment to unlock powerful set bonuses that enhance your character's abilities.
                    </p>
                  </div>
                  
                  <div class="equipment-feature">
                    <h4>Enhancement</h4>
                    <p>
                      Upgrade your gear through a variety of enhancement systems, increasing their base stats and adding new properties.
                    </p>
                  </div>
                  
                  <div class="equipment-feature">
                    <h4>Potential System</h4>
                    <p>
                      Unlock hidden potential in your equipment, adding random bonus stats that can be rerolled for optimal results.
                    </p>
                  </div>
                  
                  <div class="equipment-feature">
                    <h4>Transmogrification</h4>
                    <p>
                      Customize your character's appearance with a wide variety of cosmetic options without sacrificing stats.
                    </p>
                  </div>
                </div>
              </div>
              
              <div class="equipment-image">
                <img src="https://via.placeholder.com/600x400?text=Equipment+System" alt="Equipment System" class="rounded shadow-lg" />
              </div>
            </div>
          </div>
          
          <!-- Progression Tab -->
          <div v-if="tabs.find(t => t.id === 'progression')?.active" class="tab-pane">
            <div class="progression-content">
              <h3>Character Advancement</h3>
              <p class="progression-intro">
                MapleStory offers multiple ways to progress and strengthen your character beyond just leveling up.
              </p>
              
              <div class="progression-steps">
                <div class="step-item">
                  <div class="step-number">1</div>
                  <div class="step-content">
                    <h4>Level Up</h4>
                    <p>
                      Gain experience points by defeating monsters, completing quests, and participating in events.
                      Each level increases your base stats and unlocks new content.
                    </p>
                  </div>
                </div>
                
                <div class="step-item">
                  <div class="step-number">2</div>
                  <div class="step-content">
                    <h4>Job Advancement</h4>
                    <p>
                      At specific levels, visit job instructors to advance to more specialized classes.
                      Each advancement grants access to powerful new skills and abilities.
                    </p>
                  </div>
                </div>
                
                <div class="step-item">
                  <div class="step-number">3</div>
                  <div class="step-content">
                    <h4>Gear Progression</h4>
                    <p>
                      Obtain better equipment through drops, crafting, and special events.
                      Enhance your gear to further increase their power.
                    </p>
                  </div>
                </div>
                
                <div class="step-item">
                  <div class="step-number">4</div>
                  <div class="step-content">
                    <h4>Mastery Systems</h4>
                    <p>
                      Unlock various mastery systems like Hyper Skills, Link Skills, and Legion System
                      to gain additional bonuses across your entire account.
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.system-section {
  background-color: white;
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

.tabs-container {
  max-width: 1000px;
  margin: 0 auto;
}

.tabs-header {
  display: flex;
  justify-content: center;
  margin-bottom: var(--space-8);
  border-bottom: 2px solid var(--color-neutral-200);
  overflow-x: auto;
  padding-bottom: var(--space-2);
}

.tab-button {
  padding: var(--space-3) var(--space-6);
  background: transparent;
  border: none;
  font-size: var(--font-size-lg);
  font-weight: 600;
  color: var(--color-neutral-600);
  cursor: pointer;
  transition: all var(--transition-normal) var(--transition-function);
  border-bottom: 3px solid transparent;
  margin: 0 var(--space-2);
}

.tab-button:hover {
  color: var(--color-primary-500);
}

.tab-button.active {
  color: var(--color-primary-500);
  border-bottom-color: var(--color-primary-500);
}

.tabs-content {
  min-height: 400px;
}

/* Classes Tab */
.classes-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: var(--space-6);
}

.class-card {
  display: flex;
  flex-direction: column;
  overflow: hidden;
  height: 100%;
}

.class-image {
  width: 100%;
  text-align: center;
  padding: var(--space-4);
}

.class-image img {
  width: 120px;
  height: 120px;
  object-fit: cover;
  border-radius: var(--radius-full);
  border: 3px solid var(--color-primary-100);
}

.class-info {
  padding: var(--space-4);
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.class-info h3 {
  margin-bottom: var(--space-2);
  color: var(--color-primary-600);
  text-align: center;
}

.class-info p {
  margin-bottom: var(--space-4);
  color: var(--color-neutral-700);
  flex-grow: 1;
}

.class-stats {
  margin-top: auto;
}

.stat-item {
  display: flex;
  align-items: center;
  margin-bottom: var(--space-2);
}

.stat-label {
  width: 40px;
  font-weight: 600;
  color: var(--color-neutral-700);
}

.stat-bar {
  flex-grow: 1;
  height: 8px;
  background-color: var(--color-neutral-200);
  border-radius: var(--radius-full);
  overflow: hidden;
}

.stat-fill {
  height: 100%;
  background-color: var(--color-primary-400);
  border-radius: var(--radius-full);
  transition: width 1s ease-out;
}

/* Skills Tab */
.skills-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-8);
}

.skills-image img {
  width: 100%;
  height: auto;
}

.skills-text h3 {
  color: var(--color-secondary-600);
  margin-bottom: var(--space-4);
}

.skills-text h4 {
  color: var(--color-primary-500);
  margin-top: var(--space-6);
  margin-bottom: var(--space-2);
}

.skills-text p {
  color: var(--color-neutral-700);
  line-height: 1.6;
}

/* Equipment Tab */
.equipment-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-8);
}

.equipment-text h3 {
  color: var(--color-secondary-600);
  margin-bottom: var(--space-4);
}

.equipment-text > p {
  margin-bottom: var(--space-6);
  color: var(--color-neutral-700);
  line-height: 1.6;
}

.equipment-features {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-6);
}

.equipment-feature h4 {
  color: var(--color-primary-500);
  margin-bottom: var(--space-2);
}

.equipment-feature p {
  color: var(--color-neutral-700);
}

.equipment-image img {
  width: 100%;
  height: auto;
}

/* Progression Tab */
.progression-content {
  text-align: center;
}

.progression-content h3 {
  color: var(--color-secondary-600);
  margin-bottom: var(--space-4);
}

.progression-intro {
  max-width: 700px;
  margin: 0 auto var(--space-10);
  color: var(--color-neutral-700);
  font-size: var(--font-size-lg);
}

.progression-steps {
  display: flex;
  flex-direction: column;
  gap: var(--space-8);
  max-width: 800px;
  margin: 0 auto;
}

.step-item {
  display: flex;
  text-align: left;
  gap: var(--space-4);
}

.step-number {
  flex-shrink: 0;
  width: 40px;
  height: 40px;
  border-radius: var(--radius-full);
  background-color: var(--color-primary-400);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: var(--font-size-xl);
}

.step-content h4 {
  color: var(--color-primary-500);
  margin-bottom: var(--space-2);
}

.step-content p {
  color: var(--color-neutral-700);
}

@media (min-width: 640px) {
  .classes-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .equipment-features {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 768px) {
  .skills-content,
  .equipment-content {
    grid-template-columns: 1fr 1fr;
    align-items: center;
  }
}

@media (min-width: 1024px) {
  .classes-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>