<template>
    <NavBar></NavBar>
    <router-view v-slot="{ Component }">
        <Transition name="page-slide" mode="out-in">
            <component :is="Component"></component>
        </Transition>
    </router-view>
</template>
<script>
import NavBar from '@/components/NavBar.vue'
export default {
    components: {
        NavBar
    }
}
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600&display=swap");

body {
    font-family: "Poppins", sans-serif;
}

h1,
h2,
h3,
h5,
p,
span {
    letter-spacing: 1.2px;
}

/* BUTTON */
.btn-wrapper {
    margin-top: 18px;
}

.btn {
    border: none;
    padding: 12px 24px;
    border-radius: 24px;
    font-size: 12px;
    font-size: 0.8rem;
    letter-spacing: 2px;
    cursor: pointer;
}

.btn+.btn {
    margin-left: 10px;
}

.outline {
    background: transparent;
    color: rgba(0, 212, 255, 0.9);
    border: 1px solid rgba(2, 115, 138, 0.6);
    transition: all .3s ease;
    color: rgb(2, 118, 134);
    font-weight: 550;
}

.outline:hover {
    transform: scale(1.125);
    border-color: rgba(1, 18, 112, 0.9);
    transition: all .3s ease;
    color: rgb(2, 87, 143);
    font-weight: 600;
}

.fill {
    background-color: rgba(0, 212, 255, 0.9);
    color: rgba(255, 255, 255, 0.95);
    filter: drop-shadow(0);
    font-weight: bold;
    transition: all .3s ease;
}

.fill:hover {
    transform: scale(1.125);
    background-color: rgba(0, 212, 255, 0.9);
    border-color: rgba(255, 255, 255, 0.9);
    filter: drop-shadow(0 10px 5px rgba(0, 0, 0, 0.125));
    transition: all .3s ease;
}

/* END OF BUTTON */


/* Social Media Icons */
.social-media-list {
    position: relative;
    font-size: 20px;
    text-align: center;
    width: 100%;
    margin: 0 auto;
    padding: 0;
}

.social-media-list a i {
    color: white;
}

.social-media-list a {
    position: relative;
    display: inline-block;
    height: 55px;
    width: 55px;
    margin: 5px 15px;
    line-height: 55px;
    border-radius: 50%;
    background-color: rgb(27, 27, 27);
    cursor: pointer;
    transition: all .2s ease-in-out;
}

.social-media-list a:after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 55px;
    height: 55px;
    line-height: 55px;
    border-radius: 50%;
    opacity: 0;
    box-shadow: 0 0 0 1px #fff;
    transition: all .2s ease-in-out;
}

.social-media-list a:hover {
    background-color: #22cef4;
}

.social-media-list a:hover:after {
    opacity: 1;
    transform: scale(1.12);
    transition-timing-function: cubic-bezier(0.37, 0.74, 0.15, 1.65);
}

.social-media-list a:hover i {
    color: #000;
}

/* Begin Media Queries*/
@media screen and (max-width: 850px) {
    .social-media-list i {
        height: 55px;
        width: 55px;
        line-height: 55px;
    }

    .social-media-list i:after {
        width: 55px;
        height: 55px;
        line-height: 55px;
    }
}

.page-slide-enter-active,
.page-slide-leave-active {
    transition: 400ms ease all;
}

.page-slide-enter-from,
.page-slide-leave-to {
    opacity: 0;
    transform: translateY(60px);
}
</style>
