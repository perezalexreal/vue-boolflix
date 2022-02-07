<template>
    <div class="main-container">
        <film-box :listFilm="filmList" />
        <series-box :listSerie="serieList"/>
    </div>
</template>


<script>
import FilmBox from './FilmBox.vue'
import SeriesBox from './SeriesBox.vue'

export default {
    components: {
        FilmBox,
        SeriesBox
    },
    props: {
         filmList : Array,
         serieList: Array
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