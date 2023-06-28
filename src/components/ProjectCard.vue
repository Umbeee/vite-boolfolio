<script>
export default {
    name: "ProjectCard",
    props: ['SingleCardData']
}
</script>

<template>
    <div class="card text-start">
        <img class="card-img-top" :src="SingleCardData.cover_image" :alt="SingleCardData.title">
        <div class="card-body text-break">
            <h4 class="card-title">{{ SingleCardData.title }}</h4>
            <p class="card-text">{{ SingleCardData.content }}</p>
        </div>
    </div>
</template>

<style lang="scss"></style>