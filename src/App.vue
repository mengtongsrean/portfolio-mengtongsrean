<template>
  <div class="app-root">
    <NavBar></NavBar>
    <router-view v-slot="{ Component }">
      <Transition name="page-fade" mode="out-in">
        <component :is="Component"></component>
      </Transition>
    </router-view>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
export default {
  components: { NavBar }
}
</script>

<style>
/* ── Google Fonts ── */
@import url("https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600;700&family=DM+Mono:wght@400;500&display=swap");

/* ── Reset & Base ── */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  background-color: #080810;
  scroll-behavior: smooth;
}

body {
  font-family: 'Sora', sans-serif;
  background-color: #080810;
  color: #e8e6f0;
  min-height: 100vh;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow-x: hidden;
}

#app,
.app-root {
  background-color: #080810;
  min-height: 100vh;
}

/* ── Typography defaults ── */
h1, h2, h3, h4, h5, h6 {
  font-family: 'Sora', sans-serif;
  color: #f0eeff;
  letter-spacing: -0.02em;
  line-height: 1.2;
}

p, span, li {
  letter-spacing: 0.01em;
  line-height: 1.7;
}

/* ── Scrollbar ── */
::-webkit-scrollbar {
  width: 6px;
}
::-webkit-scrollbar-track {
  background: #080810;
}
::-webkit-scrollbar-thumb {
  background: rgba(124, 111, 234, 0.35);
  border-radius: 3px;
}
::-webkit-scrollbar-thumb:hover {
  background: rgba(124, 111, 234, 0.6);
}

/* ── Selection ── */
::selection {
  background: rgba(124, 111, 234, 0.3);
  color: #f0eeff;
}

/* ── Page transition ── */
.page-fade-enter-active,
.page-fade-leave-active {
  transition: opacity 0.25s ease, transform 0.25s ease;
}

.page-fade-enter-from {
  opacity: 0;
  transform: translateY(16px);
}

.page-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

/* ── Section line decoration ── */
.line {
  width: 48px;
  height: 3px;
  background: linear-gradient(135deg, #7c6fea, #14b8a6);
  border-radius: 2px;
  margin-top: 8px;
}
</style>