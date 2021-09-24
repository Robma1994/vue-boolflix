<template>
<div>
  <li v-for="(ele, index) in listMain" :key="index">
    {{ ele.title }}
    {{ ele.original_title }} 
    {{ ele.original_language }} 
    {{ ele.vote_count }}
  </li>
</div>
</template>

<script>
export default {
  name: 'Main',
  props: ['listMain']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
