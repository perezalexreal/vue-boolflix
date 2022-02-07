<template>
  <div>
    <h1>Film</h1>
    <div class="container">
      <div class="box-film" v-for="(film, index) in listFilm" :key="index">
        <img :src="firstPath + film.poster_path" alt="" />
        <h1 class="title">{{ film.original_title }}</h1>
        <h3 class="original-title">{{ film.title }}</h3>
        <span>Lingua:</span>
        <div class="flag-container">
          <img :src="`/flags/${film.original_language}.png`" />
        </div>
        <p class="vote">{{ film.vote_average }}</p>
        <i class="fas fa-star" v-for="(star,index) in Math.round(film.vote_average)" :key="index" ></i>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      firstPath: "https://image.tmdb.org/t/p/w500",
    };
  },
  props: {
    listFilm: Array,
  },
};
</script>


<style lang="scss" scoped>
div {
  h1 {
    text-align: center;
  }
  .container {
    padding: 50px 0px;
    display: flex;
    margin: 0 auto;
    justify-content: space-around;
    flex-wrap: wrap;
    width: 1200px;

    img {
      width: 200px;
      max-width: 300px;
    }

    .flag-container img {
        width: 20px;
        margin: 15px 0px
    }
  }
  .box-film {
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