<template>
  <div id="app">
    <header>
      <MyHeader :genres="genresList" @changeGenre="startSearch" />
    </header>
    <main>
      <Dischi :selectedGenre="genreToSearch" @genresReady="getGenresList" />
    </main>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import Dischi from './components/Dischi.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
    Dischi
  },
  data() {
    return{
      genresList: [],
      genreToSearch: "",
    };
  },
  methods: {
    getGenresList(allGenres) {
      this.genresList = allGenres;
    },
    startSearch(genreToSearch) {
      this.genreToSearch = genreToSearch;
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@1,300;1,400&family=Ubuntu:wght@300;500&display=swap');
*{
  margin: 0;
  padding: 0;
}
body{
  background-color: rgb(30, 45, 59);
  font-family: 'Ubuntu', sans-serif;
}
</style>
