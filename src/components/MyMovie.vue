<template>
  <div>
        <div>
          {{movieObject.title}}
        </div>
        <div>
          {{movieObject.original_title}}
        </div>
        <div>
          <lang-flag :iso="movieObject.original_language"/>
        </div>
        <div>
          {{Math.round(movieObject.vote_average/2)}}
        </div>
        <div>
          <img :src="`http://image.tmdb.org/t/p/w500/${movieObject.poster_path}`" alt="">
        </div>
        <div >
          <font-awesome-icon icon="fa-solid fa-star"/>
        </div>

  </div>
  
</template>

<script>
import LangFlag from "vue-lang-code-flags"

export default {
  name: 'MyMovie',
  components: {
    LangFlag
  },
  methods: {
    starRating() {
      
    }

  },
  props: {
    movieObject: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    
</style>