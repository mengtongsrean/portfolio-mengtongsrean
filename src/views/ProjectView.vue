<template>
    <div class="container project-page">
        <div class="row latest-project">
            <h1>My <span class="latest-project-h1">Latest Project</span></h1>
        </div>
        <div class="row">
            <div class="col-lg-4 col-md-6 col-xs-6">
                <img src="@/assets/images/latest-project/latestpro1.png" class="d-block w-100 img-fluid"
                    alt="Dynamic Football Store">
            </div>
            <div class="col-lg-8 col-md-6 col-xs-6 latest-project-detail">
                <h2 class="latest-project-title">Dynamic Football Store</h2>
                <div class="latest-project-tech-stack text-muted">
                    <span>&bull; Vue Js</span><span>&bull; Bootstrap</span><span>&bull; MongoDB</span><span>&bull;
                        Express Js</span>
                </div>
                <p class="latest-project-description">A full-stack e-commere website called <span>Dynamic Store</span>
                    includes features such as product listing, add-and-delete items to favourite,
                    search, sort/filter options, user authentication, cart save-and-remove functionality, purchase
                    functionality, and a dedicated dashboard for admin to add new product. It
                    is built using Vue.js for the frontend, Node.js and Express for the backend, JWT web token for
                    authentication and MongoDB for the database.</p>
                <div class="btn-wrapper d-flex align-items-center">
                    <a href="https://mengtongsrean.github.io/Dynamic-Store/" target="_blank" class="btn outline">Live
                        Demo</a>
                    <a href="https://github.com/mengtongsrean/Dynamic-Store" target="_blank" class="btn fill">More on
                        Github</a>
                </div>
            </div>
        </div>
        <div class="row more-project">
            <h1>More Projects</h1>
        </div>
        <div>
            <div class="row">
                <ProjectCard v-for="(moreProject, index) in moreProjects" :key="index" :project="moreProject"
                    :background-image="require(`@/assets/images/more-project/${moreProject.bgImgPath}`)">
                </ProjectCard>
            </div>
        </div>
    </div>
</template>
<script>
import ProjectCard from '@/components/ProjectCard.vue'

export default {
    components: {
        ProjectCard
    },
    data() {
        return {
            moreProjects: [
                {
                    title: 'Grocery List',
                    description: 'A web-based grocery list app where users can add or remove items dynamically. HTML and CSS are used for the interface, while JavaScript handles real-time data with Firebase. Items are added via an input field and "Add to Cart" button, and removed by double-clicking',
                    imgPath: 'grocery-list-app.png',
                    bgImgPath: 'bg-project.jpg',
                    liveDemoUrl: 'https://mengtongsrean.github.io/Grocery-List/',
                    gitHubUrl: 'https://github.com/mengtongsrean/Grocery-List'
                },
                {
                    title: 'Save Tracker (Chrome Extension)',
                    description: '"Saves Tracker" a Chrome extension, saves URLs from active tabs into a list stored in local storage. It offers clickable links and a delete-all feature',
                    imgPath: 'chrome-extension.png',
                    bgImgPath: 'bg-project3.jpg',
                    liveDemoUrl: 'https://mengtongsrean.github.io/Chrome-Extension/',
                    gitHubUrl: 'https://github.com/mengtongsrean/Chrome-Extension'
                },
                {
                    title: 'Youtube Clone',
                    description: 'This project is a YouTube clone built with HTML and CSS. The sidebar offers navigation links, and the main section displays a responsive grid of video previews. The CSS mimics YouTube design with responsive layouts, tooltips, hover effects, and Google Fonts for consistent typography',
                    imgPath: 'youtube-clone.png',
                    bgImgPath: 'bg-project.jpg',
                    liveDemoUrl: 'https://mengtongsrean.github.io/youtube-clone/',
                    gitHubUrl: 'https://github.com/mengtongsrean/youtube-clone'
                }
            ]
        }
    }
}


</script>


<style scoped>
img {
    box-shadow: rgba(14, 30, 37, 0.12) 0px 2px 4px 0px, rgba(14, 30, 37, 0.32) 0px 2px 16px 0px;
    border-radius: 10px;
}

/* LATEST PROJECT SECTION */
.project-page {
    margin-top: 20px;
    margin-bottom: 80px;
}

.latest-project {
    margin-top: 30px;
    margin-bottom: 40px;
}

.latest-project-h1 {
    background: -webkit-linear-gradient(#f25c37, #6b0707);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    border-bottom: 2px solid rgb(182, 4, 4);
}

.latest-project-tech-stack span {
    margin-right: 20px;
    font-size: 14px;
}

.latest-project-description {
    color: rgb(89, 82, 82);
    margin: 20px 0;
    font-size: 14px;
    line-height: 140%;
    letter-spacing: 1.7px;
}

.latest-project-description span {
    font-weight: bold;
}

.more-project {
    margin-top: 60px;
    margin-bottom: 20px;
}

/* END OF LATEST PROJECT */

/* Responsive Styles */
@media (max-width: 768px) {
    * {
        text-align: center;
    }

    h1 {
        font-size: 35px;
    }

    .latest-project {
        margin: 40px 0;
    }

    .latest-project-detail {
        margin-top: 25px;
    }

    .btn-wrapper {
        display: flex;
        justify-content: center;
    }

}
</style>