<template>
    <!-- Navbar Component -->
    <nav class="navbar navbar-expand-lg navbar-light">
        <div class="container align-items-center">
            <!-- Brand Name -->
            <div>
                <div class="navbar-brand nav-h1">Mengtong.</div>
            </div>
            <div>
                <!-- Navbar Toggler for mobile view -->
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent"
                    aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
            </div>
            <!-- Navbar Links -->
            <div class="collapse navbar-collapse justify-content-end" id="navbarSupportedContent">
                <ul class="navbar-nav">
                    <!-- Home Link -->
                    <li class="nav-item">
                        <router-link class="nav-link" aria-current="page" to="/">HOME</router-link>
                    </li>
                    <!-- About Me Link -->
                    <li class="nav-item">
                        <router-link class="nav-link" to="/about-me">ABOUT ME</router-link>
                    </li>
                    <!-- Experience Link -->
                    <li class="nav-item">
                        <router-link class="nav-link" to="/skill">SKILLS</router-link>
                    </li>
                    <!-- Project Link -->
                    <li class="nav-item">
                        <router-link class="nav-link" to="/project">PROJECTS</router-link>
                    </li>
                    <!-- Links for regular users -->
                    <li class="nav-item">
                        <router-link class="nav-link" to="/contact">CONTACT ME</router-link>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>
<style scoped>
.navbar {
    padding-top: 48px;
    padding-bottom: 48px;
}

.nav-link,
.navbar-brand {
    color: black;
    font-size: large;
    letter-spacing: 0.09rem;
}

.nav-h1 {
    background: -webkit-linear-gradient(rgba(0, 212, 255, 0.9), #9c9c9c);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: 23px;
    font-weight: 700;
}

.nav-item {
    margin-right: 35px;
    /* any value */
}

.nav-item:last-child {
    margin-right: 0;
    /* zeros out margin on last li */
}

/* router-link underline styling */
.nav-link {
    position: relative;
    color: #000;
    text-decoration: none;
    font-weight: 420;
}

.nav-link::before {
    content: "";
    position: absolute;
    display: block;
    width: 100%;
    height: 2px;
    bottom: 0;
    left: 0;
    background: -webkit-linear-gradient(#f25c37, #6b0707);
    transform: scaleX(0);
    transition: transform 0.3s ease;
}

.nav-link:hover,
.nav-link.router-link-active {
    background: -webkit-linear-gradient(#f25c37, #6b0707);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;

}

.nav-link:hover::before {
    transform: scaleX(1);
}

@media (max-width: 768px) {
    .skill-item {
        justify-content: flex-start;
    }

    .navbar {
        padding-top: 20px;
        padding-bottom: 35px;
    }
}
</style>
