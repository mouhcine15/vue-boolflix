<template>
  <div id="app">
    <MovieList/>
  </div>
</template>

<script>
import MovieList from './components/MovieList.vue'

export default {
  name: 'App',
  components: {
    MovieList
  }
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
