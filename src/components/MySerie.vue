<template>
        <div>
          {{serieObject.name}}
          <div>
              <lang-flag :iso="serieObject.original_language"/>
          </div>
        </div>
</template>

<script>
export default {
  name: 'MySerie',
  props: {
    serieObject: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    
</style>