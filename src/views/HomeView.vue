<template>
  <div class="home-wrapper">
    <div class="bg-canvas">
      <div class="orb orb-1"></div>
      <div class="orb orb-2"></div>
      <div class="orb orb-3"></div>
      <div class="grid-lines"></div>
    </div>

    <div class="container home-page">
      <div class="hero-center">

        <div class="tag-line reveal delay-1">
          <span class="dot"></span> Available for work
        </div>

        <h1 class="hero-title reveal delay-2">
          Hey, I'm <span class="name-highlight">Mengtong Srean</span>
        </h1>

        <p class="typing-text reveal delay-3">
          I am a <span class="typing-words"></span>
        </p>

        <p class="bio reveal delay-4">
          Third-year student at Swinburne University of Technology,
          majoring in Software Development.
        </p>

        <div class="btn-group reveal delay-5">
          <router-link to="/about-me" class="btn-outline-custom">More About Me</router-link>
          <a class="btn-fill-custom" href="/" download>
            <span>Get My CV</span>
            <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M21 15v4a2 2 0 01-2 2H5a2 2 0 01-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>
          </a>
        </div>

        <ul class="social-list reveal delay-6">
          <li>
            <a href="https://github.com/mengtongsrean" target="_blank" aria-label="GitHub">
              <svg width="19" height="19" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
            </a>
          </li>
          <li>
            <a href="https://www.linkedin.com/in/mengtongsrean" target="_blank" aria-label="LinkedIn">
              <svg width="19" height="19" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            </a>
          </li>
          <li>
            <a href="mailto:mengtongsrean17@gmail.com" aria-label="Email">
              <svg width="19" height="19" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
            </a>
          </li>
          <li>
            <a href="tel:+61475679863" aria-label="Phone">
              <svg width="19" height="19" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 9.8 19.79 19.79 0 01.22 1.18 2 2 0 012.2 0h3a2 2 0 012 1.72 12.84 12.84 0 00.7 2.81 2 2 0 01-.45 2.11L6.91 7.09a16 16 0 006 6l.46-.46a2 2 0 012.11-.45 12.84 12.84 0 002.81.7A2 2 0 0122 14.92v2z"/></svg>
            </a>
          </li>
        </ul>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  mounted() {
    const words = ['Software Developer', 'Web Developer', 'Problem Solver']
    let wordIndex = 0
    let charIndex = 0
    let isDeleting = false
    const typingEl = document.querySelector('.typing-words')

    function type() {
      if (!typingEl) return
      const current = words[wordIndex]
      if (isDeleting) {
        typingEl.textContent = current.substring(0, charIndex - 1)
        charIndex--
      } else {
        typingEl.textContent = current.substring(0, charIndex + 1)
        charIndex++
      }
      if (!isDeleting && charIndex === current.length) {
        setTimeout(() => { isDeleting = true }, 1800)
      } else if (isDeleting && charIndex === 0) {
        isDeleting = false
        wordIndex = (wordIndex + 1) % words.length
      }
      setTimeout(type, isDeleting ? 60 : 100)
    }
    setTimeout(type, 600)
  }
}
</script>

<style scoped>
.home-wrapper {
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
  width: 580px;
  height: 580px;
  background: radial-gradient(circle, rgba(124,111,234,0.2) 0%, transparent 70%);
  top: -160px;
  left: -160px;
  animation: floatOrb 14s ease-in-out infinite alternate;
}

.orb-2 {
  width: 480px;
  height: 480px;
  background: radial-gradient(circle, rgba(20,184,166,0.15) 0%, transparent 70%);
  bottom: -120px;
  right: -120px;
  animation: floatOrb 18s ease-in-out infinite alternate-reverse;
}

.orb-3 {
  width: 320px;
  height: 320px;
  background: radial-gradient(circle, rgba(200,80,120,0.10) 0%, transparent 70%);
  top: 55%;
  left: 55%;
  transform: translate(-50%, -50%);
  animation: pulsOrb 10s ease-in-out infinite;
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
  to   { transform: translate(60px, 50px); }
}
@keyframes pulsOrb {
  0%, 100% { opacity: 0.5; transform: translate(-50%,-50%) scale(1); }
  50%       { opacity: 1;   transform: translate(-50%,-50%) scale(1.25); }
}

.home-page {
  position: relative;
  z-index: 1;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-center {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  max-width: 680px;
  width: 100%;
  padding: 60px 20px;
}

/* Reveal animation */
.reveal {
  opacity: 0;
  transform: translateY(22px);
  animation: fadeUp 0.65s ease forwards;
}
.delay-1 { animation-delay: 0.10s; }
.delay-2 { animation-delay: 0.25s; }
.delay-3 { animation-delay: 0.40s; }
.delay-4 { animation-delay: 0.55s; }
.delay-5 { animation-delay: 0.70s; }
.delay-6 { animation-delay: 0.85s; }

@keyframes fadeUp {
  to { opacity: 1; transform: translateY(0); }
}

/* Tag pill */
.tag-line {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(124,111,234,0.1);
  border: 1px solid rgba(124,111,234,0.28);
  border-radius: 100px;
  padding: 6px 18px;
  font-size: 12.5px;
  color: #a89ff5;
  letter-spacing: 0.07em;
  margin-bottom: 28px;
  font-family: 'DM Mono', monospace;
}

.dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #4ade80;
  box-shadow: 0 0 7px #4ade80;
  animation: blinkDot 2s ease-in-out infinite;
}
@keyframes blinkDot {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0.25; }
}

/* Hero title */
.hero-title {
  font-family: 'Sora', sans-serif;
  font-size: clamp(2.4rem, 5.5vw, 4rem);
  font-weight: 700;
  line-height: 1.15;
  color: #f0eeff;
  margin-bottom: 20px;
  letter-spacing: -0.025em;
}

.name-highlight {
  background: linear-gradient(135deg, #7c6fea 0%, #14b8a6 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* Typing */
.typing-text {
  font-family: 'Sora', sans-serif;
  font-size: 1.1rem;
  color: rgba(232,230,240,0.55);
  margin-bottom: 14px;
}

.typing-words {
  color: #a89ff5;
  font-weight: 600;
  border-right: 2px solid #7c6fea;
  padding-right: 3px;
  animation: cursorBlink 0.75s step-end infinite;
}
@keyframes cursorBlink {
  0%, 100% { border-color: #7c6fea; }
  50%       { border-color: transparent; }
}

/* Bio */
.bio {
  font-family: 'Sora', sans-serif;
  font-size: 0.96rem;
  color: rgba(232,230,240,0.5);
  line-height: 1.75;
  margin-bottom: 36px;
}

/* Buttons */
.btn-group {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
  justify-content: center;
  margin-bottom: 36px;
}

.btn-outline-custom,
.btn-fill-custom {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 12px 28px;
  border-radius: 9px;
  font-family: 'Sora', sans-serif;
  font-size: 0.88rem;
  font-weight: 600;
  letter-spacing: 0.04em;
  text-decoration: none;
  cursor: pointer;
  transition: all 0.22s ease;
}

.btn-outline-custom {
  background: transparent;
  border: 1px solid rgba(124,111,234,0.45);
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
  box-shadow: 0 8px 28px rgba(124,111,234,0.35);
}

/* Social icons */
.social-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  gap: 12px;
  justify-content: center;
}

.social-list a {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 42px;
  height: 42px;
  border-radius: 10px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);
  color: rgba(232,230,240,0.55);
  transition: all 0.22s ease;
  text-decoration: none;
}
.social-list a:hover {
  background: rgba(124,111,234,0.12);
  border-color: rgba(124,111,234,0.4);
  color: #a89ff5;
  transform: translateY(-3px);
}

/* Responsive */
@media (max-width: 576px) {
  .hero-title { font-size: 2rem; }
  .btn-outline-custom,
  .btn-fill-custom { padding: 11px 22px; font-size: 0.84rem; }
}
</style>