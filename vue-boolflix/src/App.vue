<template>
  <div id="app">
<header-box @search="searchMovies" />
<main-container :filmList="filmLists"/>
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
      filmLists : [],
      seriesList : []
    }
  },
  methods: {
     searchMovies(titleInput){
        this.filmLists = this.callApi(titleInput, 'movie') 
    },
    callApi(titleInput, type) {
      let params = {
        query: titleInput,
        api_key: 'd6c26e58bb0a1dea45eecf5da7b4fd26'
      }

       axios.get(`https://api.themoviedb.org/3/search/${type}`, { params }
      ).then(( result ) => {
        this.filmLists = result.data.results;
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


</style>
