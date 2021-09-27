<template>
  <div>
    <div class="container-large">
      <div class="container-small">
        <SingleCard v-for="(ele, index) in listMain" :key="index"
          :elemento = ele
        />
      </div>
    </div>
    
  </div>
</template>

<script>
import SingleCard from './SingleCard.vue'
export default {
  name: 'Main',
  components: {
    SingleCard
  },
  props: ['listMain']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/variables';
.container-large {
  width: 100%;
  height: 2000px;
  background-color: $backgroundMain;

    .container-small{
      width: 1250px;
      margin: 0 auto;
      display: flex;
      flex-wrap: wrap;
      padding: 65px 0 65px 0;
    }
}



</style>
