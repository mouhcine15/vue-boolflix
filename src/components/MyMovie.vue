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
          {{movieObject.vote_average}}
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
  props: {
    movieObject: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    
</style>