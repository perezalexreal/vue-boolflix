<template>
<div >
     <h1> Series TV </h1>
     <div class="container">
             <div class="box-serie" v-for="(serie,index) in listSerie" :key="index">
        <img :src="firstPath+serie.poster_path" alt="">
        <h1 class="title">{{ serie.original_name}}</h1>
        <h3 class="original-title"> {{ serie.name }}</h3>
        <p class="language">{{ serie.original_language}} </p>
        <p class="vote">{{ serie.vote_average }}</p>
    </div>
     </div>

</div>
</template>


<script>
export default {
    data () {
        return {
            firstPath: 'https://image.tmdb.org/t/p/w500'
        }
    },
    props: {
       listSerie: Array
    }
}
</script>


<style lang="scss" scoped>
div {

h1 {
text-align: center;
}
    .container {
    padding: 50px 0px;
    display: flex;
    margin:0 auto;
    justify-content: space-around;
    flex-wrap: wrap;
    width: 1200px;
     
    img {
        width: 200px;
    }
}
.box-serie {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 300px;
    margin: 15px 0px;
    text-align: center;
   
        h1 {
            font-size: 24px;
        }
}
}



</style>