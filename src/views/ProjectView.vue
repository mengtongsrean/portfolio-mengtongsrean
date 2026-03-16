<template>
  <div class="projects-wrapper">

    <div class="bg-canvas">
      <div class="orb orb-1"></div>
      <div class="orb orb-2"></div>
      <div class="grid-lines"></div>
    </div>

    <div class="container projects-page">

      <!-- ── Page Header ── -->
      <div class="page-header reveal">
        <span class="section-tag">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
          Portfolio
        </span>
        <h1 class="page-title">My Projects</h1>
        <p class="page-sub">Things I've built — from full-stack apps to browser tools.</p>
      </div>

      <!-- ── Featured Project ── -->
      <section class="featured-section reveal delay-1">
        <div class="featured-label">
          <span class="pulse-dot"></span> Featured Project
        </div>
        <div class="featured-card">
          <div class="featured-img-col">
            <div class="featured-img-wrap">
              <img src="@/assets/images/latest-project/latestpro1.png" alt="Dynamic Football Store" />
              <div class="img-overlay"></div>
            </div>
          </div>
          <div class="featured-content">
            <h2 class="featured-title">Dynamic Football Store</h2>
            <div class="tech-stack">
              <span class="tech-pill">Vue.js</span>
              <span class="tech-pill">Bootstrap</span>
              <span class="tech-pill">MongoDB</span>
              <span class="tech-pill">Express.js</span>
              <span class="tech-pill">Node.js</span>
              <span class="tech-pill">JWT</span>
            </div>
            <p class="featured-desc">
              A full-stack e-commerce platform featuring product listings, favourites, search, sort &amp; filter,
              user authentication, cart management, purchase flow, and an admin dashboard for product management.
              Built with Vue.js on the frontend and Node/Express with MongoDB on the backend.
            </p>
            <div class="featured-btns">
              <a href="https://mengtongsrean.github.io/Dynamic-Store/" target="_blank" class="btn-outline-custom">
                <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 014 10 15.3 15.3 0 01-4 10 15.3 15.3 0 01-4-10 15.3 15.3 0 014-10z"/></svg>
                Live Demo
              </a>
              <a href="https://github.com/mengtongsrean/Dynamic-Store" target="_blank" class="btn-fill-custom">
                <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
                View on GitHub
              </a>
            </div>
          </div>
        </div>
      </section>

      <!-- ── More Projects ── -->
      <section class="more-section">
        <div class="section-heading reveal">
          <span class="section-tag">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M3 3h8v8H3zm10 0h8v8h-8zM3 13h8v8H3zm13 0h-3v3h3v-3zm0 5h-3v3h3v-3zm2-5h3v3h-3v-3zm0 5h3v3h-3v-3z"/></svg>
            More Work
          </span>
          <h2 class="section-title">Other Projects</h2>
        </div>

        <div class="projects-grid">
          <div
            v-for="(project, index) in moreProjects"
            :key="index"
            class="project-card reveal"
            :style="{ animationDelay: (index * 0.12) + 's' }"
          >
            <div class="project-card-img">
              <img
                :src="require(`@/assets/images/more-project/${project.imgPath}`)"
                :alt="project.title"
              />
              <div class="project-card-overlay">
                <div class="overlay-links">
                  <a :href="project.liveDemoUrl" target="_blank" class="overlay-btn">
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 014 10 15.3 15.3 0 01-4 10 15.3 15.3 0 01-4-10 15.3 15.3 0 014-10z"/></svg>
                    Demo
                  </a>
                  <a :href="project.gitHubUrl" target="_blank" class="overlay-btn overlay-btn--gh">
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
                    GitHub
                  </a>
                </div>
              </div>
            </div>
            <div class="project-card-body">
              <h3 class="project-card-title">{{ project.title }}</h3>
              <p class="project-card-desc">{{ project.description }}</p>
              <div class="project-card-footer">
                <a :href="project.liveDemoUrl" target="_blank" class="card-link">
                  Live Demo
                  <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
                </a>
                <a :href="project.gitHubUrl" target="_blank" class="card-link">
                  GitHub
                  <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>

    </div>
  </div>
</template>

<script>
import ProjectCard from '@/components/ProjectCard.vue'

export default {
  name: 'ProjectsView',
  components: { ProjectCard },
  data() {
    return {
      moreProjects: [
        {
          title: 'Grocery List',
          description: 'A web-based grocery list app where users can add or remove items dynamically. HTML and CSS for the interface, JavaScript handles real-time data with Firebase. Items added via input field and removed by double-clicking.',
          imgPath: 'grocery-list-app.png',
          bgImgPath: 'bg-project.jpg',
          liveDemoUrl: 'https://mengtongsrean.github.io/Grocery-List/',
          gitHubUrl: 'https://github.com/mengtongsrean/Grocery-List'
        },
        {
          title: 'Save Tracker (Chrome Extension)',
          description: 'A Chrome extension that saves URLs from active tabs into a persistent list stored in local storage. Offers clickable links and a delete-all feature for quick tab management.',
          imgPath: 'chrome-extension.png',
          bgImgPath: 'bg-project3.jpg',
          liveDemoUrl: 'https://mengtongsrean.github.io/Chrome-Extension/',
          gitHubUrl: 'https://github.com/mengtongsrean/Chrome-Extension'
        },
        {
          title: 'Youtube Clone',
          description: 'A YouTube clone built with HTML and CSS featuring a sidebar navigation, responsive video preview grid, tooltips, hover effects, and Google Fonts — closely mimicking the real YouTube UI.',
          imgPath: 'youtube-clone.png',
          bgImgPath: 'bg-project.jpg',
          liveDemoUrl: 'https://mengtongsrean.github.io/youtube-clone/',
          gitHubUrl: 'https://github.com/mengtongsrean/youtube-clone'
        }
      ]
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
.projects-wrapper {
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
  width: 520px;
  height: 520px;
  background: radial-gradient(circle, rgba(124,111,234,0.16) 0%, transparent 70%);
  top: -120px;
  left: -120px;
  animation: floatOrb 15s ease-in-out infinite alternate;
}

.orb-2 {
  width: 440px;
  height: 440px;
  background: radial-gradient(circle, rgba(20,184,166,0.12) 0%, transparent 70%);
  bottom: -80px;
  right: -80px;
  animation: floatOrb 19s ease-in-out infinite alternate-reverse;
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
  to   { transform: translate(55px, 45px); }
}

/* ── Page layout ── */
.projects-page {
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
.delay-1 { animation-delay: 0.15s; }

@keyframes fadeUp {
  to { opacity: 1; transform: translateY(0); }
}

/* ── Shared components ── */
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

/* ── Featured label ── */
.featured-label {
  display: flex;
  align-items: center;
  gap: 8px;
  font-family: 'DM Mono', monospace;
  font-size: 12px;
  color: #a89ff5;
  letter-spacing: 0.08em;
  margin-bottom: 16px;
}

.pulse-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #7c6fea;
  box-shadow: 0 0 8px rgba(124,111,234,0.7);
  animation: pulseDot 2s ease-in-out infinite;
}

@keyframes pulseDot {
  0%, 100% { opacity: 1; box-shadow: 0 0 8px rgba(124,111,234,0.7); }
  50%       { opacity: 0.5; box-shadow: 0 0 3px rgba(124,111,234,0.3); }
}

/* ── Featured card ── */
.featured-section {
  margin-bottom: 80px;
}

.featured-card {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 18px;
  overflow: hidden;
  transition: border-color 0.3s ease;
}

.featured-card:hover {
  border-color: rgba(124,111,234,0.25);
}

.featured-img-col {
  position: relative;
  min-height: 300px;
}

.featured-img-wrap {
  position: relative;
  width: 100%;
  height: 100%;
}

.featured-img-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.img-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to right, transparent 60%, rgba(8,8,16,0.6));
}

.featured-content {
  padding: 40px 36px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.featured-title {
  font-family: 'Sora', sans-serif;
  font-size: 1.55rem;
  font-weight: 700;
  color: #f0eeff;
  letter-spacing: -0.02em;
  margin: 0 0 14px;
}

.tech-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 20px;
}

.tech-pill {
  font-family: 'DM Mono', monospace;
  font-size: 11px;
  padding: 4px 12px;
  border-radius: 100px;
  background: rgba(124,111,234,0.1);
  border: 1px solid rgba(124,111,234,0.22);
  color: #a89ff5;
  letter-spacing: 0.04em;
}

.featured-desc {
  font-family: 'Sora', sans-serif;
  font-size: 0.89rem;
  color: rgba(232,230,240,0.5);
  line-height: 1.75;
  margin: 0 0 28px;
}

.featured-btns {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.btn-outline-custom,
.btn-fill-custom {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  padding: 10px 22px;
  border-radius: 8px;
  font-family: 'Sora', sans-serif;
  font-size: 0.84rem;
  font-weight: 600;
  letter-spacing: 0.03em;
  text-decoration: none;
  cursor: pointer;
  transition: all 0.22s ease;
}

.btn-outline-custom {
  background: transparent;
  border: 1px solid rgba(124,111,234,0.4);
  color: #a89ff5;
}
.btn-outline-custom:hover {
  background: rgba(124,111,234,0.1);
  border-color: #7c6fea;
  color: #c4bcff;
  transform: translateY(-2px);
}

.btn-fill-custom {
  background: linear-gradient(135deg, #7c6fea, #14b8a6);
  border: none;
  color: #fff;
}
.btn-fill-custom:hover {
  opacity: 0.85;
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(124,111,234,0.3);
}

/* ── More projects ── */
.more-section {
  margin-top: 20px;
}

.section-heading {
  margin-bottom: 32px;
}

.section-title {
  font-family: 'Sora', sans-serif;
  font-size: clamp(1.5rem, 3vw, 2rem);
  font-weight: 700;
  color: #f0eeff;
  letter-spacing: -0.02em;
  margin: 0;
}

/* ── Projects grid ── */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.project-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 14px;
  overflow: hidden;
  transition: border-color 0.25s ease, transform 0.25s ease;
  display: flex;
  flex-direction: column;
}

.project-card:hover {
  border-color: rgba(124,111,234,0.25);
  transform: translateY(-4px);
}

.project-card-img {
  position: relative;
  height: 200px;
  overflow: hidden;
  background: #13131f;
}

.project-card-img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: top;
  display: block;
  transition: transform 0.4s ease;
}

.project-card:hover .project-card-img img {
  transform: scale(1.05);
}

.project-card-overlay {
  position: absolute;
  inset: 0;
  background: rgba(8,8,16,0.75);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.25s ease;
}

.project-card:hover .project-card-overlay {
  opacity: 1;
}

.overlay-links {
  display: flex;
  gap: 10px;
}

.overlay-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 8px 16px;
  border-radius: 8px;
  font-family: 'Sora', sans-serif;
  font-size: 0.8rem;
  font-weight: 600;
  text-decoration: none;
  background: rgba(124,111,234,0.2);
  border: 1px solid rgba(124,111,234,0.4);
  color: #c4bcff;
  transition: all 0.2s ease;
}

.overlay-btn:hover {
  background: rgba(124,111,234,0.35);
}

.overlay-btn--gh {
  background: rgba(255,255,255,0.08);
  border-color: rgba(255,255,255,0.15);
  color: #e8e6f0;
}

.overlay-btn--gh:hover {
  background: rgba(255,255,255,0.15);
}

/* Card body */
.project-card-body {
  padding: 20px;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.project-card-title {
  font-family: 'Sora', sans-serif;
  font-size: 0.97rem;
  font-weight: 600;
  color: #e8e6f0;
  margin: 0 0 10px;
  letter-spacing: -0.01em;
}

.project-card-desc {
  font-family: 'Sora', sans-serif;
  font-size: 0.82rem;
  color: rgba(232,230,240,0.45);
  line-height: 1.65;
  margin: 0 0 16px;
  flex: 1;
}

.project-card-footer {
  display: flex;
  gap: 16px;
  border-top: 1px solid rgba(255,255,255,0.06);
  padding-top: 14px;
}

.card-link {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  font-family: 'DM Mono', monospace;
  font-size: 11.5px;
  color: rgba(232,230,240,0.4);
  text-decoration: none;
  letter-spacing: 0.04em;
  transition: color 0.2s ease;
}

.card-link:hover {
  color: #a89ff5;
}

/* ── Responsive ── */
@media (max-width: 991px) {
  .featured-card {
    grid-template-columns: 1fr;
  }

  .featured-img-col {
    min-height: 220px;
  }

  .img-overlay {
    background: linear-gradient(to bottom, transparent 50%, rgba(8,8,16,0.7));
  }

  .featured-content {
    padding: 28px 24px;
  }

  .projects-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }

  .projects-page {
    padding-top: 100px;
  }

  .featured-title {
    font-size: 1.3rem;
  }
}
</style>