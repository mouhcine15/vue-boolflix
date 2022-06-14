<template>
  <div class="hello">
    <input type="text">
    <button>Invio</button>
    <div>
        <MyMovie
            v-for="(element, i) in movies" 
            :key="i"
            :movieObject="element"/>
    </div>
  </div>
</template>

<script>
import axios from "axios"
import MyMovie from './MyMovie.vue'

export default {
  name: 'MovieList',
  components: {
    MyMovie
  },

    data () {
      return {
          apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=6e5cb1250b73157692bdf4c00483dc2b&language=it-IT&query=matrix",
          movies: []
      }
    },
    created() {
      axios.get(this.apiUrl)
      .then(result => {
          this.movies = result.data.results;
          console.log(result)
      })
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    #hello {
        background-color: aqua;
    }
</style>