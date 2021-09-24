<template>
<div class="header">
  <div>
    <h1>BoolFlix</h1>
  </div>
  <form>
      <input v-model="researchUser" type="text" placeholder="Research movies">
      <button @click.prevent="$emit('clickBtn', researchUser)">Research Film</button>
   </form>
</div>
  
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      researchUser: ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/variables';
.header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100%;
  height: 100px;
  background-color: $backgroundHeader;

    h1 {
      color: $colorTitle;
    }
}

</style>
