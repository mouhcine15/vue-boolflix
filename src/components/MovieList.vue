<template>
  <div class="hello">
    <div id="header">
      <div id="logo">
        <h1><strong>BOOLFLIX</strong></h1>
      </div>
      <div>
        <input type="text" v-model="searching" @keyup.enter="searchMovie">
        <button @click="searchMovie">Invio</button>
      </div>
    </div>
    <div id="componenti">
        <MyMovie
            v-for="element in movies" 
            :key="element.i"
            :movieObject="element"/>
        <MySerieVue
            v-for="item in series" 
            :key="item.index"
            :serieObject="item"/>
    </div>
  </div>
</template>

<script>
import axios from "axios"
import MyMovie from './MyMovie.vue'
import MySerieVue from './MySerie.vue'

export default {
  name: 'MovieList',
  components: {
    MyMovie,
    MySerieVue
},

    data () {
      return {
          apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=6e5cb1250b73157692bdf4c00483dc2b&language=it-IT&query=matrix",
          movies: [],

          apiUrlSerie: "https://api.themoviedb.org/3/search/tv?api_key=6e5cb1250b73157692bdf4c00483dc2b&language=it_IT&query=scrubs",
          series: [],

          searching: ""
      }
    },
    created() {
      axios.get(this.apiUrl)
      .then(result => {
          this.movies = result.data.results;
          console.log(result)
      })
  },
  methods: {
    searchMovie() {
      this.apiUrl= "https://api.themoviedb.org/3/search/movie?api_key=6e5cb1250b73157692bdf4c00483dc2b&language=it-IT&query=" + this.searching;
      axios.get(this.apiUrl)
      .then(result => {
          this.movies = result.data.results;
          console.log(result)
      }),
      this.searchSerie()
    },
    searchSerie() {
      this.apiUrlSerie= "https://api.themoviedb.org/3/search/tv?api_key=6e5cb1250b73157692bdf4c00483dc2b&language=it-IT&query=" + this.searching;
      axios.get(this.apiUrlSerie)
      .then(result => {
          this.series = result.data.results;
          console.log(result)
      })
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #header {
    background-color: black;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
  }
  #logo {
    color: red;
  }
  #componenti {
    background-color: rgb(55, 54, 54);
  }
  input {
    width: 250px;
    height: 30px;
  }
  button {
    width: 100px;
    height: 30px;
  }
</style>