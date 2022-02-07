<template>
    <div class="main-container">
        <film-box :listFilm="filmList" />
    </div>
</template>


<script>
import FilmBox from './FilmBox.vue'


export default {
    components: {
        FilmBox
    },
    props: {
         filmList : Array
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