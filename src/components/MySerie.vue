<template>
  <div class="container">
    <div id="poster">
      <div id="immagine">
        <img :src="`http://image.tmdb.org/t/p/w342/${serieObject.poster_path}`" alt="">
      </div>
      <div id="testo">
        <div>
          {{serieObject.name}}
        </div>
        <div>
          {{serieObject.original_name}}
        </div>
        <div>
          <lang-flag :iso="serieObject.original_language"/>
        </div>
        <div >
          <font-awesome-icon v-for="i in starRating(serieObject.vote_average)" :key="i" icon="fa-solid fa-star" />
          <font-awesome-icon v-for="index in starRatingEmpty(serieObject.vote_average)" :key="index" icon="fa-regular fa-star" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MySerie',
  props: {
    serieObject: Object
  },
  methods: {
    starRating(rating) {
      let calc = parseInt(Math.round(rating/2))
      console.log(calc);
      return calc;
    },
    starRatingEmpty(rating) {
      let calcEmpty = parseInt(Math.round(5-(rating/2)))
      console.log(calcEmpty);
      return calcEmpty;
    }
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
      z-index: 3;
      background-color: black;
    }
    .fa-star {
      color: yellow;
    }
</style>