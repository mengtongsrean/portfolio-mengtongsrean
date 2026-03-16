<template>
  <div class="contact-wrapper">

    <div class="bg-canvas">
      <div class="orb orb-1"></div>
      <div class="orb orb-2"></div>
      <div class="grid-lines"></div>
    </div>

    <div class="container contact-page">

      <!-- ── Header ── -->
      <div class="page-header reveal">
        <span class="section-tag">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>
          Contact
        </span>
        <h1 class="page-title">Let's Work Together</h1>
        <p class="page-sub">Have a project in mind or just want to say hi? My inbox is always open.</p>
      </div>

      <!-- ── Two columns ── -->
      <div class="contact-grid">

        <!-- ── Form ── -->
        <div class="form-col reveal delay-1">
          <form ref="contactForm" @submit.prevent="handleSubmit" novalidate>
            <input type="hidden" name="access_key" value="b9843fb4-93d3-4c91-af3b-1a618984ef45">

            <div class="form-row">
              <div class="form-group">
                <label for="fname">First name</label>
                <input type="text" id="fname" name="fname" v-model="firstname" placeholder="Mengtong" />
                <span v-if="errors.firstname" class="field-error">{{ errors.firstname }}</span>
              </div>
              <div class="form-group">
                <label for="lname">Last name</label>
                <input type="text" id="lname" name="lname" v-model="lastname" placeholder="Srean" />
                <span v-if="errors.lastname" class="field-error">{{ errors.lastname }}</span>
              </div>
            </div>

            <div class="form-group">
              <label for="email">Email</label>
              <input type="email" id="email" name="email" v-model="email" placeholder="you@example.com" />
              <span v-if="errors.email" class="field-error">{{ errors.email }}</span>
            </div>

            <div class="form-group">
              <label for="message">Message</label>
              <textarea id="message" name="message" v-model="textmessage" rows="6" placeholder="Drop your message here..."></textarea>
            </div>

            <button type="submit" class="submit-btn" :class="{ loading: isLoading }">
              <span v-if="!isLoading">
                Send Message
                <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg>
              </span>
              <span v-else class="loading-text">Sending...</span>
            </button>

            <!-- Result message -->
            <div v-if="resultMsg" class="result-msg" :class="resultType">
              <svg v-if="resultType === 'success'" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="20 6 9 17 4 12"/></svg>
              <svg v-else width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>
              {{ resultMsg }}
            </div>
          </form>
        </div>

        <!-- ── Info ── -->
        <div class="info-col reveal delay-2">

          <div class="info-card">
            <h3 class="info-heading">Reach me directly</h3>

            <ul class="contact-list">
              <li class="contact-item">
                <div class="contact-icon">
                  <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
                </div>
                <div class="contact-detail">
                  <span class="contact-label">Location</span>
                  <span class="contact-value">Springvale, VIC 3171, Australia</span>
                </div>
              </li>
              <li class="contact-item">
                <div class="contact-icon">
                  <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
                </div>
                <div class="contact-detail">
                  <span class="contact-label">Email</span>
                  <a href="mailto:mengtongsrean17@gmail.com" class="contact-value contact-link">mengtongsrean17@gmail.com</a>
                </div>
              </li>
              <li class="contact-item">
                <div class="contact-icon">
                  <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 9.8 19.79 19.79 0 01.22 1.18 2 2 0 012.2 0h3a2 2 0 012 1.72 12.84 12.84 0 00.7 2.81 2 2 0 01-.45 2.11L6.91 7.09a16 16 0 006 6l.46-.46a2 2 0 012.11-.45 12.84 12.84 0 002.81.7A2 2 0 0122 14.92v2z"/></svg>
                </div>
                <div class="contact-detail">
                  <span class="contact-label">Phone</span>
                  <a href="tel:+61475679863" class="contact-value contact-link">+61 475 679 863</a>
                </div>
              </li>
            </ul>

            <div class="divider"></div>

            <p class="social-label">Find me on</p>
            <div class="social-row">
              <a href="https://github.com/mengtongsrean" target="_blank" aria-label="GitHub" class="social-btn">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
              </a>
              <a href="https://www.linkedin.com/in/mengtongsrean" target="_blank" aria-label="LinkedIn" class="social-btn">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
              </a>
              <a href="mailto:mengtongsrean17@gmail.com" aria-label="Email" class="social-btn">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
              </a>
              <a href="https://www.instagram.com/mengtong.srean/" target="_blank" aria-label="Instagram" class="social-btn">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>
              </a>
            </div>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactView',
  data() {
    return {
      errors: {},
      firstname: '',
      lastname: '',
      email: '',
      textmessage: '',
      isLoading: false,
      resultMsg: '',
      resultType: ''
    }
  },
  methods: {
    validateEmail(email) {
      return /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/.test(email)
    },
    validateForm() {
      this.errors = {}
      const namePattern = /^[A-Za-z]+$/
      if (!this.firstname || !this.firstname.match(namePattern))
        this.errors.firstname = 'First name must contain letters only.'
      if (!this.lastname || !this.lastname.match(namePattern))
        this.errors.lastname = 'Last name must contain letters only.'
      if (!this.email || !this.validateEmail(this.email))
        this.errors.email = 'Please enter a valid email address.'
      return Object.keys(this.errors).length === 0
    },
    async handleSubmit() {
      if (!this.validateForm()) return
      const form = this.$refs.contactForm
      this.isLoading = true
      this.resultMsg = ''

      try {
        const formData = new FormData(form)
        const jsonData = JSON.stringify(Object.fromEntries(formData))
        const response = await fetch('https://api.web3forms.com/submit', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json', Accept: 'application/json' },
          body: jsonData
        })
        const result = await response.json()
        this.resultMsg = response.ok ? result.message : result.message
        this.resultType = response.ok ? 'success' : 'error'
        if (response.ok) {
          this.firstname = ''
          this.lastname = ''
          this.email = ''
          this.textmessage = ''
        }
      } catch {
        this.resultMsg = 'Something went wrong. Please try again.'
        this.resultType = 'error'
      } finally {
        this.isLoading = false
        setTimeout(() => { this.resultMsg = '' }, 5000)
      }
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
.contact-wrapper {
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
  width: 500px; height: 500px;
  background: radial-gradient(circle, rgba(124,111,234,0.16) 0%, transparent 70%);
  top: -100px; left: -100px;
  animation: floatOrb 16s ease-in-out infinite alternate;
}

.orb-2 {
  width: 420px; height: 420px;
  background: radial-gradient(circle, rgba(20,184,166,0.12) 0%, transparent 70%);
  bottom: -80px; right: -80px;
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
  from { transform: translate(0,0); }
  to   { transform: translate(50px, 40px); }
}

/* ── Page ── */
.contact-page {
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
.delay-1 { animation-delay: 0.1s; }
.delay-2 { animation-delay: 0.22s; }

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
.page-header { margin-bottom: 52px; }

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

/* ── Two-column grid ── */
.contact-grid {
  display: grid;
  grid-template-columns: 1fr 420px;
  gap: 32px;
  align-items: start;
}

/* ── Form ── */
.form-col form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 7px;
}

.form-group label {
  font-family: 'DM Mono', monospace;
  font-size: 12px;
  color: rgba(232,230,240,0.45);
  letter-spacing: 0.06em;
}

.form-group input,
.form-group textarea {
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.09);
  border-radius: 10px;
  padding: 12px 16px;
  font-family: 'Sora', sans-serif;
  font-size: 0.88rem;
  color: #e8e6f0;
  outline: none;
  transition: border-color 0.2s ease, background 0.2s ease;
  resize: none;
  width: 100%;
}

.form-group input::placeholder,
.form-group textarea::placeholder {
  color: rgba(232,230,240,0.25);
}

.form-group input:focus,
.form-group textarea:focus {
  border-color: rgba(124,111,234,0.5);
  background: rgba(124,111,234,0.05);
}

.field-error {
  font-family: 'DM Mono', monospace;
  font-size: 11px;
  color: #f87171;
  letter-spacing: 0.03em;
}

/* ── Submit button ── */
.submit-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 13px 32px;
  background: linear-gradient(135deg, #7c6fea, #14b8a6);
  border: none;
  border-radius: 10px;
  font-family: 'Sora', sans-serif;
  font-size: 0.9rem;
  font-weight: 600;
  color: #fff;
  cursor: pointer;
  transition: all 0.22s ease;
  width: fit-content;
}

.submit-btn:hover {
  opacity: 0.88;
  transform: translateY(-2px);
  box-shadow: 0 8px 28px rgba(124,111,234,0.3);
}

.submit-btn.loading {
  opacity: 0.6;
  cursor: not-allowed;
  transform: none;
}

/* ── Result message ── */
.result-msg {
  display: flex;
  align-items: center;
  gap: 8px;
  font-family: 'Sora', sans-serif;
  font-size: 0.875rem;
  padding: 12px 16px;
  border-radius: 10px;
  margin-top: 4px;
}

.result-msg.success {
  background: rgba(20,184,166,0.1);
  border: 1px solid rgba(20,184,166,0.22);
  color: #5eead4;
}

.result-msg.error {
  background: rgba(248,113,113,0.08);
  border: 1px solid rgba(248,113,113,0.2);
  color: #f87171;
}

/* ── Info card ── */
.info-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 16px;
  padding: 32px 28px;
}

.info-heading {
  font-family: 'Sora', sans-serif;
  font-size: 1rem;
  font-weight: 600;
  color: #e8e6f0;
  margin: 0 0 24px;
  letter-spacing: -0.01em;
}

/* ── Contact list ── */
.contact-list {
  list-style: none;
  padding: 0;
  margin: 0 0 24px;
  display: flex;
  flex-direction: column;
  gap: 18px;
}

.contact-item {
  display: flex;
  align-items: flex-start;
  gap: 14px;
}

.contact-icon {
  width: 34px;
  height: 34px;
  border-radius: 9px;
  background: rgba(124,111,234,0.1);
  border: 1px solid rgba(124,111,234,0.18);
  color: #a89ff5;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  margin-top: 2px;
}

.contact-detail {
  display: flex;
  flex-direction: column;
  gap: 3px;
}

.contact-label {
  font-family: 'DM Mono', monospace;
  font-size: 11px;
  color: rgba(232,230,240,0.35);
  letter-spacing: 0.06em;
}

.contact-value {
  font-family: 'Sora', sans-serif;
  font-size: 0.875rem;
  color: rgba(232,230,240,0.7);
}

.contact-link {
  text-decoration: none;
  transition: color 0.2s ease;
}

.contact-link:hover {
  color: #a89ff5;
}

/* ── Divider ── */
.divider {
  height: 1px;
  background: rgba(255,255,255,0.07);
  margin: 24px 0;
}

/* ── Social ── */
.social-label {
  font-family: 'DM Mono', monospace;
  font-size: 11px;
  color: rgba(232,230,240,0.35);
  letter-spacing: 0.06em;
  margin: 0 0 14px;
}

.social-row {
  display: flex;
  gap: 10px;
}

.social-btn {
  width: 40px;
  height: 40px;
  border-radius: 10px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);
  color: rgba(232,230,240,0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  transition: all 0.2s ease;
}

.social-btn:hover {
  background: rgba(124,111,234,0.12);
  border-color: rgba(124,111,234,0.35);
  color: #a89ff5;
  transform: translateY(-2px);
}

/* ── Responsive ── */
@media (max-width: 991px) {
  .contact-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 576px) {
  .contact-page { padding-top: 100px; }
  .form-row { grid-template-columns: 1fr; }
  .page-title { font-size: 2rem; }
}
</style>