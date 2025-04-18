<script setup lang="ts">
defineProps<{
  id?: string
}>()
</script>

<template>
  <section :id="id" class="introduction-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">歡迎來到新楓之谷的奇幻世界</h2>
        <p class="section-subtitle">展開屬於你的冒險旅程，探索多采多姿的楓之谷宇宙</p>
      </div>
      
      <div class="intro-content">
        <div class="intro-image">
          <img src="https://via.placeholder.com/600x400?text=MapleStory+World" alt="新楓之谷世界" class="rounded shadow-lg" />
        </div>
        
        <div class="intro-text">
          <h3>魔法冒險，即刻啟程</h3>
          <p>
            新楓之谷是一款免費遊玩的2D橫向卷軸大型多人線上角色扮演遊戲，自2003年推出以來，以可愛像素畫風、豐富劇情與多元玩法，深受全球玩家喜愛[1][3]。
          </p>
          
          <h3>楓之谷的故事</h3>
          <p>
            很久以前，強大的黑魔法師威脅著楓之谷的和平。五位英雄挺身對抗，雖然最終失敗卻將黑魔法師封印於冰中。數百年後，你將成為新一代冒險者，踏上拯救世界的旅程[1][3]。
          </p>
          
          <div class="intro-features">
            <div class="feature-item">
              <div class="feature-icon">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="icon">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 10l-2 1m0 0l-2-1m2 1v2.5M20 7l-2 1m2-1l-2-1m2 1v2.5M14 4l-2-1-2 1M4 7l2-1M4 7l2 1M4 7v2.5M12 21l-2-1m2 1l2-1m-2 1v-2.5M6 18l-2-1v-2.5M18 18l2-1v-2.5" />
                </svg>
              </div>
              <div class="feature-content">
                <h4>廣闊世界</h4>
                <p>探索各具特色的地區與地圖，從福爾摩沙、西門町到未來東京，冒險無窮[1][3]。</p>
              </div>
            </div>
            
            <div class="feature-item">
              <div class="feature-icon">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="icon">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
                </svg>
              </div>
              <div class="feature-content">
                <h4>社群互動</h4>
                <p>加入公會、結交夥伴，一同挑戰強敵與副本，享受團隊合作的樂趣[2]。</p>
              </div>
            </div>
            
            <div class="feature-item">
              <div class="feature-icon">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="icon">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
                </svg>
              </div>
              <div class="feature-content">
                <h4>持續進化</h4>
                <p>定期推出全新職業、活動與內容，冒險永不止步[2]。</p>
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