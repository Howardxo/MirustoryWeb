<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const props = defineProps<{}>()
const emit = defineEmits(['navigate'])

const isMenuOpen = ref(false)
const isScrolled = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}

const navigateTo = (sectionId: string) => {
  emit('navigate', sectionId)
  closeMenu()
}

const checkScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', checkScroll)
  checkScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', checkScroll)
})
</script>

<template>
  <header :class="['site-header', { 'scrolled': isScrolled }]">
    <div class="container">
      <nav class="navbar">
        <div class="logo">
          <a href="#" @click.prevent="navigateTo('top')">
            <span class="logo-text">MiruStory</span>
          </a>
        </div>
        
        <div class="menu-toggle" @click="toggleMenu">
          <div :class="['hamburger', { 'active': isMenuOpen }]">
            <span></span>
            <span></span>
            <span></span>
          </div>
        </div>
        
        <ul :class="['nav-menu', { 'active': isMenuOpen }]">
          <li class="nav-item">
            <a href="#introduction" @click.prevent="navigateTo('introduction')">介紹</a>
          </li>
          <li class="nav-item">
            <a href="#system" @click.prevent="navigateTo('system')">遊戲設置</a>
          </li>
          <li class="nav-item">
            <a href="#strategy" @click.prevent="navigateTo('strategy')">攻略</a>
          </li>
          <li class="nav-item">
            <a href="#" class="btn btn-primary">開始玩</a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.site-header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: var(--z-50);
  padding: var(--space-4) 0;
  transition: all var(--transition-normal) var(--transition-function);
  background-color: transparent;
}

.site-header.scrolled {
  background-color: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(8px);
  box-shadow: var(--shadow-md);
  padding: var(--space-2) 0;
}

.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  z-index: var(--z-20);
}

/* LOGO字體顏色: 頂部白色，滑動後變主色 */
.logo-text {
  font-family: var(--font-heading);
  font-weight: 800;
  font-size: var(--font-size-xl);
  color: #fff;
  transition: color var(--transition-normal) var(--transition-function);
}
.site-header.scrolled .logo-text {
  color: var(--color-primary-600);
}

/* 導覽選單字體顏色: 頂部白色，滑動後變深色 */
.nav-menu {
  display: flex;
  align-items: center;
  list-style: none;
  gap: var(--space-8);
}
.nav-item a {
  font-weight: 600;
  color: #fff;
  transition: color var(--transition-normal) var(--transition-function);
}
.site-header.scrolled .nav-item a {
  color: var(--color-neutral-800);
}
.nav-item a:hover {
  color: var(--color-primary-500);
}

.menu-toggle {
  display: none;
  z-index: var(--z-20);
}

.hamburger {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 24px;
  height: 18px;
  cursor: pointer;
}
.hamburger span {
  display: block;
  height: 2px;
  width: 100%;
  background-color: #fff;
  transition: all 0.3s ease;
}
.site-header.scrolled .hamburger span {
  background-color: var(--color-neutral-800);
}
.hamburger.active span:nth-child(1) {
  transform: translateY(8px) rotate(45deg);
}
.hamburger.active span:nth-child(2) {
  opacity: 0;
}
.hamburger.active span:nth-child(3) {
  transform: translateY(-8px) rotate(-45deg);
}

@media (max-width: 768px) {
  .menu-toggle {
    display: block;
  }
  .nav-menu {
    position: fixed;
    top: 0;
    right: -100%;
    flex-direction: column;
    background-color: white;
    width: 80%;
    height: 100vh;
    padding: var(--space-20) var(--space-8);
    gap: var(--space-6);
    transition: right 0.3s ease;
    box-shadow: var(--shadow-xl);
  }
  .nav-menu.active {
    right: 0;
  }
  .nav-item {
    width: 100%;
    text-align: center;
  }
  .nav-item a.btn {
    width: 100%;
    margin-top: var(--space-4);
  }
  /* 手機選單內的字體顏色調整 */
  .nav-menu {
    background: #fff;
  }
  .nav-menu .nav-item a {
    color: var(--color-neutral-800);
  }
  .nav-menu .nav-item a.btn {
    color: #fff;
    background: var(--color-primary-500);
  }
}
</style>
