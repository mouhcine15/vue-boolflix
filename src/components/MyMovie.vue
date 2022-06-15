<template>
  <div>
    <ul>
      <li>
        <div>
          {{movieObject.name}}
        </div>
        <div>
          {{movieObject.title}}
        </div>
        <div>
          {{movieObject.original_title}}
        </div>
        <div>
          {{movieObject.original_language}}
        </div>
        <div>
          {{movieObject.vote_average}}
        </div>

      </li>
    </ul>
  </div>
  
</template>

<script>
export default {
  name: 'MyMovie',
  props: {
    movieObject: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    
</style>