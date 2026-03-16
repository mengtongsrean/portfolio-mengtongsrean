<template>
  <div class="skills-wrapper">

    <div class="bg-canvas">
      <div class="orb orb-1"></div>
      <div class="orb orb-2"></div>
      <div class="grid-lines"></div>
    </div>

    <div class="container skills-page">

      <!-- ── Header ── -->
      <div class="page-header reveal">
        <span class="section-tag">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"/></svg>
          Capabilities
        </span>
        <h1 class="page-title">Skills & Tools</h1>
        <p class="page-sub">Technologies I work with and tools I rely on.</p>
      </div>

      <!-- ── Skills Grid ── -->
      <div class="categories-grid">

        <!-- Front-End -->
        <div class="category-col reveal delay-1">
          <div class="category-header">
            <div class="category-icon category-icon--fe">
              <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
            </div>
            <span class="category-name">Front-End</span>
          </div>
          <div class="skills-list">
            <div
              v-for="(skill, index) in frontEndSkills"
              :key="index"
              class="skill-item"
              :style="{ animationDelay: (index * 0.07) + 's' }"
            >
              <img :src="require(`@/assets/icons/${skill.icon}`)" :alt="skill.title" class="skill-icon" />
              <div class="skill-info">
                <span class="skill-name">{{ skill.title }}</span>
                <span class="skill-badge" :class="getBadgeClass(skill.level)">{{ skill.level }}</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Back-End -->
        <div class="category-col reveal delay-2">
          <div class="category-header">
            <div class="category-icon category-icon--be">
              <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="3" width="20" height="14" rx="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg>
            </div>
            <span class="category-name">Back-End</span>
          </div>
          <div class="skills-list">
            <div
              v-for="(skill, index) in backEndSkills"
              :key="index"
              class="skill-item"
              :style="{ animationDelay: (index * 0.07) + 's' }"
            >
              <img :src="require(`@/assets/icons/${skill.icon}`)" :alt="skill.title" class="skill-icon" />
              <div class="skill-info">
                <span class="skill-name">{{ skill.title }}</span>
                <span class="skill-badge" :class="getBadgeClass(skill.level)">{{ skill.level }}</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Tools -->
        <div class="category-col reveal delay-3">
          <div class="category-header">
            <div class="category-icon category-icon--tools">
              <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14.7 6.3a1 1 0 000 1.4l1.6 1.6a1 1 0 001.4 0l3.77-3.77a6 6 0 01-7.94 7.94l-6.91 6.91a2.12 2.12 0 01-3-3l6.91-6.91a6 6 0 017.94-7.94l-3.76 3.76z"/></svg>
            </div>
            <span class="category-name">Tools</span>
          </div>
          <div class="skills-list">
            <div
              v-for="(skill, index) in tools"
              :key="index"
              class="skill-item"
              :style="{ animationDelay: (index * 0.07) + 's' }"
            >
              <img :src="require(`@/assets/icons/${skill.icon}`)" :alt="skill.title" class="skill-icon" />
              <div class="skill-info">
                <span class="skill-name">{{ skill.title }}</span>
                <span class="skill-badge" :class="getBadgeClass(skill.level)">{{ skill.level }}</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Others -->
        <div class="category-col reveal delay-4">
          <div class="category-header">
            <div class="category-icon category-icon--other">
              <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>
            </div>
            <span class="category-name">Others</span>
          </div>
          <div class="skills-list">
            <div
              v-for="(skill, index) in others"
              :key="index"
              class="skill-item"
              :style="{ animationDelay: (index * 0.07) + 's' }"
            >
              <img :src="require(`@/assets/icons/${skill.icon}`)" :alt="skill.title" class="skill-icon" />
              <div class="skill-info">
                <span class="skill-name">{{ skill.title }}</span>
                <span class="skill-badge" :class="getBadgeClass(skill.level)">{{ skill.level }}</span>
              </div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SkillsView',
  data() {
    return {
      frontEndSkills: [
        { title: 'Vue', level: 'Intermediate', icon: 'Vue.js.svg' },
        { title: 'React', level: 'Intermediate', icon: 'React.svg' },
        { title: 'JavaScript', level: 'Intermediate', icon: 'JavaScript.svg' },
        { title: 'HTML', level: 'Intermediate', icon: 'HTML5.svg' },
        { title: 'CSS', level: 'Intermediate', icon: 'CSS3.svg' },
        { title: 'Bootstrap', level: 'Intermediate', icon: 'Bootstrap.svg' },
        { title: 'MaterialUI', level: 'Intermediate', icon: 'MaterialUI.svg' }
      ],
      backEndSkills: [
        { title: 'MongoDB', level: 'Intermediate', icon: 'MongoDB.svg' },
        { title: 'MySQL', level: 'Intermediate', icon: 'MySQL.svg' },
        { title: 'NodeJs', level: 'Intermediate', icon: 'Node.js.svg' },
        { title: 'Firebase', level: 'Intermediate', icon: 'Firebase.svg' },
        { title: 'C, C++, C#', level: 'Intermediate', icon: 'C.svg' },
        { title: 'Python', level: 'Beginner', icon: 'Python.svg' },
        { title: 'FastAPI', level: 'Intermediate', icon: 'FastAPI.svg' }
      ],
      tools: [
        { title: 'Git', level: 'Intermediate', icon: 'Git.svg' },
        { title: 'Github', level: 'Intermediate', icon: 'GitHub.svg' },
        { title: 'Jira', level: 'Intermediate', icon: 'Jira.svg' },
        { title: 'Confluence', level: 'Intermediate', icon: 'Confluence.svg' },
        { title: 'Trello', level: 'Intermediate', icon: 'Trello.svg' },
        { title: 'Figma', level: 'Beginner', icon: 'Figma.svg' }
      ],
      others: [
        { title: 'Kotlin', level: 'Intermediate', icon: 'Kotlin.svg' }
      ]
    }
  },
  methods: {
    getBadgeClass(level) {
      if (level === 'Beginner') return 'badge--beginner'
      if (level === 'Intermediate') return 'badge--intermediate'
      if (level === 'Advanced') return 'badge--advanced'
      return ''
    }
  },
  mounted() {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.style.animationPlayState = 'running'
          observer.unobserve(entry.target)
        }
      })
    }, { threshold: 0.1 })

    document.querySelectorAll('.reveal').forEach(el => {
      el.style.animationPlayState = 'paused'
      observer.observe(el)
    })
  }
}
</script>

<style scoped>
/* ── Wrapper & Background ── */
.skills-wrapper {
  min-height: 100vh;
  background: #080810;
  position: relative;
  overflow: hidden;
}

.bg-canvas {
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
}

.orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(90px);
}

.orb-1 {
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, rgba(124,111,234,0.16) 0%, transparent 70%);
  top: -100px;
  right: -100px;
  animation: floatOrb 16s ease-in-out infinite alternate;
}

.orb-2 {
  width: 420px;
  height: 420px;
  background: radial-gradient(circle, rgba(20,184,166,0.12) 0%, transparent 70%);
  bottom: -80px;
  left: -80px;
  animation: floatOrb 20s ease-in-out infinite alternate-reverse;
}

.grid-lines {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,0.022) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.022) 1px, transparent 1px);
  background-size: 64px 64px;
}

@keyframes floatOrb {
  from { transform: translate(0, 0); }
  to   { transform: translate(50px, 40px); }
}

/* ── Page layout ── */
.skills-page {
  position: relative;
  z-index: 1;
  padding-top: 120px;
  padding-bottom: 100px;
}

/* ── Reveal ── */
.reveal {
  opacity: 0;
  transform: translateY(22px);
  animation: fadeUp 0.65s ease forwards;
  animation-play-state: paused;
}
.delay-1 { animation-delay: 0.05s; }
.delay-2 { animation-delay: 0.15s; }
.delay-3 { animation-delay: 0.25s; }
.delay-4 { animation-delay: 0.35s; }

@keyframes fadeUp {
  to { opacity: 1; transform: translateY(0); }
}

/* ── Section tag ── */
.section-tag {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  background: rgba(124,111,234,0.1);
  border: 1px solid rgba(124,111,234,0.25);
  border-radius: 100px;
  padding: 5px 14px;
  font-size: 12px;
  color: #a89ff5;
  letter-spacing: 0.07em;
  font-family: 'DM Mono', monospace;
  margin-bottom: 12px;
}

/* ── Page header ── */
.page-header {
  margin-bottom: 56px;
}

.page-title {
  font-family: 'Sora', sans-serif;
  font-size: clamp(2rem, 4.5vw, 3.2rem);
  font-weight: 700;
  color: #f0eeff;
  letter-spacing: -0.025em;
  margin: 0 0 10px;
}

.page-sub {
  font-family: 'Sora', sans-serif;
  font-size: 0.97rem;
  color: rgba(232,230,240,0.45);
  margin: 0;
}

/* ── Categories grid ── */
.categories-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  align-items: start;
}

/* ── Category column ── */
.category-col {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 16px;
  padding: 24px 20px;
  transition: border-color 0.25s ease;
}

.category-col:hover {
  border-color: rgba(124,111,234,0.2);
}

/* ── Category header ── */
.category-header {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 20px;
  padding-bottom: 16px;
  border-bottom: 1px solid rgba(255,255,255,0.06);
}

.category-icon {
  width: 32px;
  height: 32px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.category-icon--fe {
  background: rgba(124,111,234,0.15);
  color: #a89ff5;
  border: 1px solid rgba(124,111,234,0.2);
}

.category-icon--be {
  background: rgba(20,184,166,0.12);
  color: #5eead4;
  border: 1px solid rgba(20,184,166,0.2);
}

.category-icon--tools {
  background: rgba(251,191,36,0.1);
  color: #fcd34d;
  border: 1px solid rgba(251,191,36,0.18);
}

.category-icon--other {
  background: rgba(244,114,182,0.1);
  color: #f9a8d4;
  border: 1px solid rgba(244,114,182,0.18);
}

.category-name {
  font-family: 'Sora', sans-serif;
  font-size: 0.9rem;
  font-weight: 600;
  color: #e8e6f0;
  letter-spacing: 0.02em;
}

/* ── Skill items ── */
.skills-list {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.skill-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 12px;
  border-radius: 10px;
  background: rgba(255,255,255,0.02);
  border: 1px solid rgba(255,255,255,0.05);
  transition: all 0.2s ease;
  cursor: default;
}

.skill-item:hover {
  background: rgba(124,111,234,0.07);
  border-color: rgba(124,111,234,0.18);
  transform: translateX(4px);
}

.skill-icon {
  width: 26px;
  height: 26px;
  object-fit: contain;
  flex-shrink: 0;
}

.skill-info {
  display: flex;
  flex-direction: column;
  gap: 2px;
  min-width: 0;
}

.skill-name {
  font-family: 'Sora', sans-serif;
  font-size: 0.85rem;
  font-weight: 500;
  color: rgba(232,230,240,0.85);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

/* ── Level badges ── */
.skill-badge {
  font-family: 'DM Mono', monospace;
  font-size: 10px;
  letter-spacing: 0.05em;
  padding: 2px 8px;
  border-radius: 100px;
  width: fit-content;
}

.badge--beginner {
  background: rgba(251,191,36,0.1);
  border: 1px solid rgba(251,191,36,0.2);
  color: #fcd34d;
}

.badge--intermediate {
  background: rgba(124,111,234,0.1);
  border: 1px solid rgba(124,111,234,0.22);
  color: #a89ff5;
}

.badge--advanced {
  background: rgba(20,184,166,0.1);
  border: 1px solid rgba(20,184,166,0.22);
  color: #5eead4;
}

/* ── Responsive ── */
@media (max-width: 1100px) {
  .categories-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .categories-grid {
    grid-template-columns: 1fr;
  }

  .skills-page {
    padding-top: 100px;
  }

  .page-title {
    font-size: 2rem;
  }
}
</style>