<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container align-items-center">

      <!-- Brand -->
      <router-link to="/" class="navbar-brand nav-brand">Mengtong.</router-link>

      <!-- Mobile toggler -->
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="toggler-icon"></span>
        <span class="toggler-icon"></span>
        <span class="toggler-icon"></span>
      </button>

      <!-- Links -->
      <div class="collapse navbar-collapse justify-content-end" id="navbarSupportedContent">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/about-me">About Me</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/skill">Skills</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/project">Projects</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link nav-link-cta" to="/contact">Contact Me</router-link>
          </li>
        </ul>
      </div>

    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  padding: 20px 0;
  background: rgba(8, 8, 16, 0.7);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
  transition: padding 0.3s ease;
}

/* Brand */
.nav-brand {
  font-family: 'Sora', sans-serif;
  font-size: 1.3rem;
  font-weight: 700;
  letter-spacing: -0.02em;
  text-decoration: none;
  background: linear-gradient(135deg, #7c6fea, #14b8a6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* Nav links */
.navbar-nav {
  gap: 4px;
  align-items: center;
}

.nav-link {
  font-family: 'Sora', sans-serif;
  font-size: 0.85rem;
  font-weight: 500;
  letter-spacing: 0.05em;
  color: rgba(232, 230, 240, 0.6) !important;
  text-decoration: none;
  padding: 7px 14px !important;
  border-radius: 7px;
  transition: all 0.2s ease;
  position: relative;
}

.nav-link:hover {
  color: #e8e6f0 !important;
  background: rgba(255, 255, 255, 0.06);
}

.nav-link.router-link-active {
  color: #a89ff5 !important;
  background: rgba(124, 111, 234, 0.1);
}

/* Contact CTA button */
.nav-link-cta {
  background: rgba(124, 111, 234, 0.15) !important;
  border: 1px solid rgba(124, 111, 234, 0.3) !important;
  color: #a89ff5 !important;
  padding: 7px 18px !important;
  margin-left: 6px;
}

.nav-link-cta:hover {
  background: rgba(124, 111, 234, 0.25) !important;
  border-color: rgba(124, 111, 234, 0.5) !important;
  color: #c4bcff !important;
}

.nav-link-cta.router-link-active {
  background: rgba(124, 111, 234, 0.25) !important;
  color: #c4bcff !important;
}

/* Custom hamburger */
.navbar-toggler {
  background: transparent;
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: 8px;
  padding: 8px 10px;
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
}

.navbar-toggler:focus {
  box-shadow: none;
  outline: none;
}

.toggler-icon {
  display: block;
  width: 20px;
  height: 2px;
  background: rgba(232, 230, 240, 0.7);
  border-radius: 2px;
  transition: all 0.2s ease;
}

/* Mobile collapse */
@media (max-width: 991px) {
  .navbar-toggler {
    display: flex;      /* ← only visible on mobile */
  }
  .navbar-collapse {
    margin-top: 16px;
    padding: 16px;
    background: rgba(8, 8, 16, 0.95);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 12px;
  }

  .navbar-nav {
    gap: 4px;
  }

  .nav-link {
    display: block;
    padding: 10px 14px !important;
  }

  .nav-link-cta {
    margin-left: 0;
    margin-top: 6px;
    text-align: center;
    display: block;
  }
}
</style>