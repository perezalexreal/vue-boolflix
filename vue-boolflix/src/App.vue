<template>
  <div id="app">
<header-box @search="searchInput" />
<main-container :filmList="filmLists" :serieList="serieLists"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderBox from './components/HeaderBox.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
    MainContainer
  },
  data () {
    return {
      firstPath: 'https://image.tmdb.org/t/p/w500',
      filmLists : [],
      serieLists : []
    }
  },
  methods: {
     searchMovies(titleInput){
       this.callApi(titleInput, 'movie') 
    },
     searchSeries(titleInput){
        this.callApi(titleInput, 'tv') 
    },
    searchInput(titleInput){
      this.searchMovies(titleInput);
      this.searchSeries(titleInput);
    },
    callApi(titleInput, type) {
      let params = {
        query: titleInput,
        api_key: 'd6c26e58bb0a1dea45eecf5da7b4fd26'
      }

       axios.get(`https://api.themoviedb.org/3/search/${type}`, { params }
      ).then(( result ) => {
       if(type == 'tv'){
          this.serieLists = result.data.results;
       } else {
          this.filmLists = result.data.results;
       }
      })
    }
  }
}
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
 @import '/scss/main.scss'

</style>
