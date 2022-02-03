<template>
    <div class="main-container">
        <film-box />
        <film-box />
        <film-box />
        <film-box />
        <film-box />
        <film-box />
        <film-box />
        <film-box />
        <film-box />
        <film-box />
        <film-box />
        <film-box />
    </div>
</template>


<script>
import FilmBox from './FilmBox.vue'


export default {
    components: {
        FilmBox
    }
}
</script>


<style lang="scss" scoped>

.main-container {
    padding: 50px 0px;
    display: flex;
    margin:0 auto;
    justify-content: space-around;
    flex-wrap: wrap;
    width: 1200px;
}

</style>