<template>
    <div class="d-flex flex-wrap justify-content-center">
        <div class="skill-container d-flex align-items-center">
            <img :src="require(`@/assets/icons/${icon}`)" alt="Project Icon" class="project-icon img-fluid" />
            <div class="flex-column">
                <div>{{ title }}</div>
                <div class="skill-level">{{ level }}</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['icon', 'title', 'level']
}
</script>
<style scoped>
.project-icon {
    width: 15%;
    margin-right: 13px;
}
</style>