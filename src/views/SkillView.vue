<template>
    <div class="container skill-page my-5">
        <div class="row">
            <h1 class="text-center">Skills</h1>
        </div>
        <div class="row">
            <p class="text-center text-muted">What I know</p>
        </div>
        <!-- Skills Section -->
        <div class="row mt-3">
            <div class="col-lg-3 col-md-4 col-sm-6 col-xs-12">
                <div class="text-center mt-5 mb-3">Front-End</div>
                <SkillCard v-for="(skill, index) in frontEndSkills" :key="index" :title="skill.title"
                    :level="skill.level" :icon="skill.icon">
                </SkillCard>
            </div>
            <div class="col-lg-3 col-md-4 col-sm-6 col-xs-12">
                <div class="text-center  mt-5 mb-3">Back-End</div>
                <SkillCard v-for="(skill, index) in backEndSkills" :key="index" :title="skill.title"
                    :level="skill.level" :icon="skill.icon">
                </SkillCard>
            </div>
            <div class="col-lg-3 col-md-4 col-sm-6 col-xs-12">
                <div class="text-center  mt-5 mb-3">Tools</div>
                <SkillCard v-for="(skill, index) in tools" :key="index" :title="skill.title"
                    :level="skill.level" :icon="skill.icon">
                </SkillCard>
            </div>
            <div class="col-lg-3 col-md-4 col-sm-6 col-xs-12">
                <div class="text-center  mt-5 mb-3">Others</div>
                <SkillCard v-for="(skill, index) in others" :key="index" :title="skill.title"
                    :level="skill.level" :icon="skill.icon">
                </SkillCard>
            </div>
        </div>
    </div>
</template>

<script>
import SkillCard from '@/components/SkillCard.vue'
export default {
    components: {
        SkillCard
    },
    data() {
        return {
            frontEndSkills: [
                { title: 'Vue', level: 'Intermediate', icon: 'Vue.js.svg'},
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
                { title: 'Kotlin', level: 'Intermediate', icon: 'Kotlin.svg' },
             ]
        }
    }
}

</script>

<style>
.skill-container {
    box-shadow: rgba(14, 30, 37, 0.12) 0px 2px 4px 0px, rgba(14, 30, 37, 0.32) 0px 2px 16px 0px;
    padding: 14px 20px;
    margin: 10px;
    width: 100%;
    max-width: 300px;
    border-radius: 15px;
}

.skill-container i {
    margin-right: 10px;
}

.skill-container .flex-column {
    margin-left: 10px;
}

.skill-level {
    font-size: 12px;
    font-weight: lighter;
    color: rgb(179, 171, 171);
}

@media (max-width: 768px) {
    .skill-container {
        max-width: 100%;
    }
}
</style>
