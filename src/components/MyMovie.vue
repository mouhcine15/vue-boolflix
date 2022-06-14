<template>
  <div>
    {{movieObject.original_title}}
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