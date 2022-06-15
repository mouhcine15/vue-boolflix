<template>
  <div>
    <ul>
      <li>
        <div>
          {{serieObject.name}}
        </div>
      </li>
    </ul>
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