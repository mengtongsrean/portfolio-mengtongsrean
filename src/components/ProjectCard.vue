<template>
    <div class="col-12 col-md-6 col-lg-4">
        <div class="card" :style="{ backgroundImage: `url(${backgroundImage})` }">
            <!-- project Image -->
            <img :src="getImagePath(project.imgPath)" :alt="project.title" class="card-img-top" />
            <div class="card-body text-center">
                <h5 class="card-title">{{ project.title }}</h5>
                <p class="card-text">{{ project.description }}</p>
            </div>
            <div class="btn-wrapper d-flex align-items-center">
                <a :href="project.liveDemoUrl" target="_blank" class="btn outline">Live Demo</a>
                <a :href="project.gitHubUrl" target="_blank" class="btn fill">More on Github</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['project', 'backgroundImage'],
    methods: {
        getImagePath(imagePath) {
            if (imagePath) {
                return require(`@/assets/images/more-project/${imagePath}`);
            }
            // Fallback image if imagePath is undefined
            return require("@/assets/images/default.jpg");
        }
    }
}
</script>

<style scoped>
.card {
    border-radius: 12px;
    border: 1px solid rgba(255, 255, 255, 0.125);
    padding: 38px;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-size: cover;
    /* Ensure background image covers the card */
    background-position: center;
    /* Center the background image */
    background-repeat: no-repeat;
    /* Prevent background image from repeating */
    color: white;
}

.card-title {
    text-transform: uppercase;
    font-size: 2rem;
    color: black;
}

.card-text {
    color: white;
    font-size: 0.8rem;
    line-height: 140%;
    letter-spacing: 1.6px;

    color: rgb(118, 114, 114);
}

.card-img-top {
    width: 100%;
    height: auto;
    object-fit: contain;
}


.outline {
    color: rgba(0, 212, 255, 0.9);
    border: 1px solid rgba(0, 212, 255, 0.6);
}

.outline:hover {
    color: rgba(26, 121, 245, 0.9);
    border-color: rgba(26, 121, 245, 0.9);
}
</style>
