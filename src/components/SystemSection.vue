<script setup lang="ts">
import { ref } from 'vue'

defineProps<{
  id?: string
}>()

const tabs = ref([
  { id: 'classes', label: '職業', active: true },
  { id: 'skills', label: '技能', active: false },
  { id: 'equipment', label: '裝備', active: false },
  { id: 'progression', label: '成長', active: false }
])

const setActiveTab = (tabId: string) => {
  tabs.value = tabs.value.map(tab => ({
    ...tab,
    active: tab.id === tabId
  }))
}

// 職業資料
const classes = [
  {
    name: '戰士',
    description: '擅長近戰與防禦，戰士能承受大量傷害並保護隊友。',
    image: 'https://via.placeholder.com/150?text=Warrior',
    stats: { strength: 90, dexterity: 40, intelligence: 30, luck: 40 }
  },
  {
    name: '法師',
    description: '精通魔法遠程攻擊，法師能施展強大咒語擊退敵人。',
    image: 'https://via.placeholder.com/150?text=Magician',
    stats: { strength: 30, dexterity: 40, intelligence: 90, luck: 40 }
  },
  {
    name: '弓箭手',
    description: '遠距離精準打擊，弓箭手善於從遠方消滅目標。',
    image: 'https://via.placeholder.com/150?text=Archer',
    stats: { strength: 40, dexterity: 90, intelligence: 30, luck: 40 }
  },
  {
    name: '盜賊',
    description: '敏捷且狡猾，盜賊能迅速出擊並消失於暗影中。',
    image: 'https://via.placeholder.com/150?text=Thief',
    stats: { strength: 40, dexterity: 70, intelligence: 30, luck: 60 }
  },
  {
    name: '海盜',
    description: '靈活多變，能近戰爆發也能遠距輸出，擁有拳霸、槍手、重砲指揮官三大分支。',
    image: 'https://via.placeholder.com/150?text=Pirate',
    stats: { strength: 70, dexterity: 70, intelligence: 30, luck: 40 }
  }
]
</script>

<template>
  <section :id="id" class="system-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">遊戲系統介紹</h2>
        <p class="section-subtitle">探索新楓之谷獨特且豐富的遊戲機制</p>
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
          <!-- 職業 -->
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
                      <span class="stat-label">力量</span>
                      <div class="stat-bar">
                        <div 
                          class="stat-fill"
                          :style="{ width: `${classItem.stats.strength}%` }"
                        ></div>
                      </div>
                    </div>
                    <div class="stat-item">
                      <span class="stat-label">敏捷</span>
                      <div class="stat-bar">
                        <div 
                          class="stat-fill"
                          :style="{ width: `${classItem.stats.dexterity}%` }"
                        ></div>
                      </div>
                    </div>
                    <div class="stat-item">
                      <span class="stat-label">智力</span>
                      <div class="stat-bar">
                        <div 
                          class="stat-fill"
                          :style="{ width: `${classItem.stats.intelligence}%` }"
                        ></div>
                      </div>
                    </div>
                    <div class="stat-item">
                      <span class="stat-label">幸運</span>
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
          
          <!-- 技能 -->
          <div v-if="tabs.find(t => t.id === 'skills')?.active" class="tab-pane">
            <div class="skills-content">
              <div class="skills-image">
                <img src="https://via.placeholder.com/600x400?text=Skills+Tree" alt="技能系統" class="rounded shadow-lg" />
              </div>
              <div class="skills-text">
                <h3>精通你的技能</h3>
                <p>
                  在新楓之谷中，角色成長取決於你選擇發展的技能。每個職業擁有獨特的主動與被動技能，可依照個人玩法自由搭配。
                </p>
                <h4>技能點數系統</h4>
                <p>
                  升級時可獲得技能點數，分配於各項技能。分配策略將決定角色強項與弱點。
                </p>
                <h4>技能樹</h4>
                <p>
                  技能以樹狀方式逐步解鎖，部分技能需先學會前置技能，讓養成更具策略性。
                </p>
                <h4>技能等級</h4>
                <p>
                  每項技能可多次升級，提升威力。你可專精單一技能或平均分配，打造專屬風格。
                </p>
              </div>
            </div>
          </div>
          
          <!-- 裝備 -->
          <div v-if="tabs.find(t => t.id === 'equipment')?.active" class="tab-pane">
            <div class="equipment-content">
              <div class="equipment-text">
                <h3>裝備強化冒險</h3>
                <p>
                  裝備是角色戰力的關鍵。收集並強化武器、防具與飾品，提升屬性並解鎖特殊能力。
                </p>
                <div class="equipment-features">
                  <div class="equipment-feature">
                    <h4>套裝效果</h4>
                    <p>
                      集齊裝備套裝可獲得強力加成，提升角色整體能力。
                    </p>
                  </div>
                  <div class="equipment-feature">
                    <h4>裝備強化</h4>
                    <p>
                      透過多種強化系統提升裝備屬性，開啟更多潛能。
                    </p>
                  </div>
                  <div class="equipment-feature">
                    <h4>潛能系統</h4>
                    <p>
                      解鎖裝備隱藏潛能，隨機獲得額外屬性，可重置以追求最佳組合。
                    </p>
                  </div>
                  <div class="equipment-feature">
                    <h4>外觀變更</h4>
                    <p>
                      多樣時裝系統，讓你自訂外觀又不影響屬性。
                    </p>
                  </div>
                </div>
              </div>
              <div class="equipment-image">
                <img src="https://via.placeholder.com/600x400?text=Equipment+System" alt="裝備系統" class="rounded shadow-lg" />
              </div>
            </div>
          </div>
          
          <!-- 成長 -->
          <div v-if="tabs.find(t => t.id === 'progression')?.active" class="tab-pane">
            <div class="progression-content">
              <h3>角色成長歷程</h3>
              <p class="progression-intro">
                新楓之谷提供多元成長路線，讓你的冒險不僅止於升級。
              </p>
              <div class="progression-steps">
                <div class="step-item">
                  <div class="step-number">1</div>
                  <div class="step-content">
                    <h4>等級提升</h4>
                    <p>
                      打怪、解任務、參與活動獲得經驗值，每升一級提升基本能力並解鎖新內容。
                    </p>
                  </div>
                </div>
                <div class="step-item">
                  <div class="step-number">2</div>
                  <div class="step-content">
                    <h4>轉職進階</h4>
                    <p>
                      達到指定等級可找轉職教官進階，獲得全新技能與專屬能力。
                    </p>
                  </div>
                </div>
                <div class="step-item">
                  <div class="step-number">3</div>
                  <div class="step-content">
                    <h4>裝備成長</h4>
                    <p>
                      透過打怪、製作、活動等方式獲得更強裝備，並進行強化提升。
                    </p>
                  </div>
                </div>
                <div class="step-item">
                  <div class="step-number">4</div>
                  <div class="step-content">
                    <h4>進階系統</h4>
                    <p>
                      解鎖超技能、連結技能、聯盟系統等進階玩法，帳號內所有角色皆可受益。
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
  background: #f7fafc;
  padding: 48px 0;
}

.section-header {
  text-align: center;
  margin-bottom: 48px;
}

.section-title {
  color: #3b82f6;
  margin-bottom: 16px;
  font-size: 2.2rem;
  font-weight: 700;
  letter-spacing: 1px;
}

.section-subtitle {
  font-size: 1.25rem;
  color: #64748b;
  max-width: 700px;
  margin: 0 auto;
}

.tabs-container {
  max-width: 1000px;
  margin: 0 auto;
}

.tabs-header {
  display: flex;
  justify-content: center;
  margin-bottom: 32px;
  border-bottom: 2px solid #e5e7eb;
  overflow-x: auto;
  padding-bottom: 8px;
}

.tab-button {
  padding: 12px 32px;
  background: none;
  border: none;
  font-size: 1.125rem;
  font-weight: 600;
  color: #64748b;
  cursor: pointer;
  border-bottom: 3px solid transparent;
  margin: 0 8px;
  transition: color 0.2s, border-bottom 0.2s;
  outline: none;
}
.tab-button:focus {
  color: #2563eb;
}
.tab-button:hover,
.tab-button.active {
  color: #2563eb;
  border-bottom-color: #2563eb;
}

.tabs-content {
  min-height: 400px;
}

/* 職業 */
.classes-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
}
@media (min-width: 640px) {
  .classes-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (min-width: 1024px) {
  .classes-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}
.class-card {
  display: flex;
  flex-direction: column;
  background: #fff;
  border-radius: 16px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.06);
  overflow: hidden;
  height: 100%;
  transition: transform 0.2s;
  contain: layout style; /* CSS優化: 提升渲染效能[3] */
}
.class-card:hover {
  transform: scale(1.03);
}
.class-image {
  width: 100%;
  text-align: center;
  padding: 24px;
}
.class-image img {
  width: 120px;
  height: 120px;
  object-fit: cover;
  border-radius: 50%;
  border: 3px solid #dbeafe;
  background: #f1f5f9;
}
.class-info {
  padding: 24px;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}
.class-info h3 {
  margin-bottom: 8px;
  color: #3b82f6;
  text-align: center;
  font-size: 1.3rem;
}
.class-info p {
  margin-bottom: 16px;
  color: #334155;
  flex-grow: 1;
  text-align: center;
}
.class-stats {
  margin-top: auto;
}
.stat-item {
  display: flex;
  align-items: center;
  margin-bottom: 8px;
}
.stat-label {
  width: 48px;
  font-weight: 600;
  color: #334155;
  font-size: 1rem;
}
.stat-bar {
  flex-grow: 1;
  height: 8px;
  background: #e5e7eb;
  border-radius: 8px;
  overflow: hidden;
  margin-left: 8px;
}
.stat-fill {
  height: 100%;
  background: linear-gradient(90deg,#60a5fa,#2563eb);
  border-radius: 8px;
  transition: width 1s cubic-bezier(.4,0,.2,1);
}

/* 技能 */
.skills-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: 32px;
}
@media (min-width: 768px) {
  .skills-content {
    grid-template-columns: 1fr 1fr;
    align-items: center;
  }
}
.skills-image img {
  width: 100%;
  height: auto;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
}
.skills-text h3 {
  color: #6366f1;
  margin-bottom: 16px;
}
.skills-text h4 {
  color: #2563eb;
  margin-top: 24px;
  margin-bottom: 8px;
}
.skills-text p {
  color: #334155;
  line-height: 1.6;
}

/* 裝備 */
.equipment-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: 32px;
}
@media (min-width: 768px) {
  .equipment-content {
    grid-template-columns: 1fr 1fr;
    align-items: center;
  }
}
.equipment-text h3 {
  color: #6366f1;
  margin-bottom: 16px;
}
.equipment-text > p {
  margin-bottom: 24px;
  color: #334155;
  line-height: 1.6;
}
.equipment-features {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
}
@media (min-width: 640px) {
  .equipment-features {
    grid-template-columns: repeat(2, 1fr);
  }
}
.equipment-feature h4 {
  color: #2563eb;
  margin-bottom: 8px;
}
.equipment-feature p {
  color: #334155;
}
.equipment-image img {
  width: 100%;
  height: auto;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
}

/* 成長 */
.progression-content {
  text-align: center;
}
.progression-content h3 {
  color: #6366f1;
  margin-bottom: 16px;
}
.progression-intro {
  max-width: 700px;
  margin: 0 auto 40px;
  color: #334155;
  font-size: 1.1rem;
}
.progression-steps {
  display: flex;
  flex-direction: column;
  gap: 32px;
  max-width: 800px;
  margin: 0 auto;
}
.step-item {
  display: flex;
  text-align: left;
  gap: 16px;
  align-items: flex-start;
}
.step-number {
  flex-shrink: 0;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: #60a5fa;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 1.25rem;
  box-shadow: 0 1px 4px rgba(0,0,0,0.06);
}
.step-content h4 {
  color: #2563eb;
  margin-bottom: 8px;
}
.step-content p {
  color: #334155;
}

@media (max-width: 767px) {
  .step-item {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
}
</style>
