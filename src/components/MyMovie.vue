<template>
  <div class="container">
    <div id="poster">
      <div id="immagine">
        <img :src="`http://image.tmdb.org/t/p/w342/${movieObject.poster_path}`" alt="">
      </div>
      <div id="testo">
        <div>
          <strong>Titolo: </strong> {{movieObject.title}}
        </div>
        <div>
          <strong>Titolo originale: </strong> {{movieObject.original_title}}
        </div>
        <div>
          <strong>Lingua: </strong> <lang-flag :iso="movieObject.original_language"/>
        </div>
        <div>
          <strong> Overview: </strong> {{movieObject.overview}}
        </div>
        <div >
          Voto: 
          <font-awesome-icon v-for="i in starRating(movieObject.vote_average)" :key="i" icon="fa-solid fa-star" />
          <font-awesome-icon v-for="i in starRatingEmpty(movieObject.vote_average)" :key="i" icon="fa-regular fa-star" />
        </div>
      </div>
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
    starRating(rating) {
      let calc = parseInt(Math.round(rating/2));
      return calc;
    },
    starRatingEmpty(rating) {
      let calcEmpty = parseInt(Math.round(5-(rating/2)));
      return calcEmpty;
    }
  },
  props: {
    movieObject: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .container {
      position: relative;
      display: inline-block;
    }
    #poster {
      position: relative;
      margin: 20px;
    }
    #immagine {
      position: relative;
      z-index: 2;
    }
    #immagine:hover {
      z-index: 0;
    }
    #testo {
      position: absolute;
      top: 0;
      height: 100%;
      width: 100%;
      color:white;
      padding: 15px;
    }
    #testo:hover {
      z-index: 2;
      background-color: black;
    }
    .fa-star {
      color: yellow;
    }
</style>