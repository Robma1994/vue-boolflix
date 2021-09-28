<template>
<div>
  <div class="singleCardContainer">
    <div class="frontCard">
     <img :src="`https://image.tmdb.org/t/p/w342/${elemento.poster_path ? elemento.poster_path : element.poster_path = null}`" alt="" class="sizeImg"> 
      <div class="retroCard" >
        <div>
          <h1> {{ elemento.title ? elemento.title : elemento.name }} </h1>
          <h2> {{ elemento.original_title ? elemento.original_title : elemento.original_name }} </h2>
          <h3> {{ elemento.original_language }} </h3>
          <p> {{ elemento.vote_count }} </p>
          <p>
            {{ elemento.overview ? elemento.overview : elemento.overview = "Non disponibile"}} 
            </p>
          <img v-if="flagExists(elemento.original_language)" class="size-img" :src="require(`../assets/bandiera-${elemento.original_language}.png`)" alt="">
        </div>
        
      </div>
    </div>
      
    
  </div>
  
</div>
</template>

<script>

export default {
  name: 'SingleCard',
  props: ['elemento'],
  methods: {
    flagExists(lang) {
      if(require(`../assets/bandiera-${lang}.png`))
        return true;
      return false;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/variables';
.singleCardContainer {
  margin: 10px 10px;
  
    .frontCard {
      height: 420px;
      width: 300px;
      
      
      .retroCard {
        height: 100%;
        background-color: $colorRetroCard;
        display: none;
        overflow-y: auto;
      }
       
        .sizeImg {
          height: 100%;
          width: 100%;
        }

    }

    li {
      list-style-type: none;
    }
    .size-img {
      width: 20px;
    }
    .frontCard:hover > img{
        display: none
    }

    .frontCard:hover .retroCard {
      display: block;
    }
}
</style>
