<template>
<div>
  <ul class="singleCardContainer">
    <li>
      {{ elemento.title }} 
      {{ elemento.original_title }} 
      {{ elemento.original_language }} 
      {{ elemento.vote_count }}
    </li>
  </ul>
  
</div>
</template>

<script>

export default {
  name: 'SingleCard',
  props: ['elemento']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.singleCardContainer {
  background-color: white;
  border: 1px solid black;
  width: 180px;
  height: 180px;

    li {
      list-style-type: none;
    }
}
</style>
