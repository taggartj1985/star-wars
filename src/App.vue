<template>
  <div>
    <h1>Star Wars</h1>
    <div>
      <film-list :films="films"></film-list>
    </div>
  </div>
</template>

<script>
import FilmList from './components/FilmList.vue';

export default {
  data(){
    return {
      films: [],
      selectedFilm: null
    }
  },
  components: {
    "film-list": FilmList,
  },
  mounted(){
    fetch('https://swapi.dev/api/films/')
    .then(res => res.json())
    .then(data => this.films = data.results)

  },
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
