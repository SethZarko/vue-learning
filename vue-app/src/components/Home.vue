<template>
    <div class="home-container">
        <Hero />
        <Blog />
    </div>
</template>

<script>
import Hero from "./Hero.vue";
import Blog from "./Blog.vue";


export default {
    name: 'Home-comp',
    components: {
        Hero,
        Blog,
    },
created() {
    document.title = "Vue Blog: Home"
},
}

</script>

<style scoped>

</style>