<template>
<div class="container">
    <div class="box-film" v-for="(film,index) in listFilm" :key="index">
        <img src="" alt="">
        <h1 class="title">{{ film.original_title }}</h1>
        <h2 class="original-title"> {{ film.title }}</h2>
        <p class="language">{{ film.original_language}} </p>
        <p class="vote">{{ film.vote_average }}</p>
    </div>
</div>
</template>


<script>
export default {
    props: {
       listFilm: Array
    }
}
</script>


<style lang="scss" scoped>

.container {
    padding: 50px 0px;
    display: flex;
    margin:0 auto;
    justify-content: space-around;
    flex-wrap: wrap;
    width: 1200px;
}
.box-film {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 300px;
    margin: 15px 0px;
    text-align: center;
}

</style>