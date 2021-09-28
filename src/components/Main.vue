<template>
  <div>
    <div class="container-large">
      <div class="container-small">
        <SingleCard 
        v-for="ele in listMain" :key="ele.id" :elemento = ele
        />

        <SingleCard 
        v-for="ele in series" :key="ele.id" :elemento = ele
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
  props: ['listMain', 'series']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/variables';
.container-large {
  width: 100%;
  background-color: $backgroundMain;
  height: 100vh;
  content: '';
  display: table;
  clear: both;
    .container-small{
      //width: 1250px;
      //margin: 0 auto;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      //padding: 65px 0 65px 0;
    }
}



</style>
