<template>
<div>
  <div class="singleCardContainer">
    <div class="frontCard">
     <img v-if="elemento.poster_path" :src="`https://image.tmdb.org/t/p/w342/${elemento.poster_path}`" alt="" class="sizeImg"> 
     <img v-else src="../assets/Boolflix.png" alt="">
    <div class="retroCard" >
      <div>
        <div>
          <h1> Title</h1>
          <p class="color">{{ elemento.title ? elemento.title : elemento.name }}</p>  
        </div>
        <div>
          <h2> Title Original </h2>
            <p class="color"> {{ elemento.original_title ? elemento.original_title : elemento.original_name }}  </p> 
        </div>
        <div>
          <h3> Original Language </h3>
          <img v-if="nation.includes(elemento.original_language)" class="size-img" :src="require(`../assets/${elemento.original_language}.png`)" alt="">
          <p v-else>Lingua non disponibile</p>
        </div>
        <div>
          <h3>Voto medio</h3>
          <i v-for="i in numberStars()" :key="i" class="fas fa-star color"></i>
        </div>
        <div>
          <h3>Recensioni</h3>
          <p class="color">{{ elemento.vote_count }}</p>
        </div>
        <div>
          <h3>Overview</h3>
          <p class="color"> {{ elemento.overview ? elemento.overview : elemento.overview = "Non disponibile"}} </p>
        </div>
        
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
  data() {
    return {
      nation: ['en','es','fr','it','nl','pl','pt','sk','zh']
    }
  },
  methods: {
    numberStars() {
      return Math.ceil(this.elemento.vote_average / 2)
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
      
        .sizeImg {
          height: 100%;
          width: 100%;
        }
        .color {
          color: white;
        }

    }

    .retroCard {
        height: 100%;
        background-color: $colorRetroCard;
        display: none;
        overflow-y: auto;

        .size-img {
          width: 20px;
        }
    }
    

    .frontCard:hover > img{
        display: none
    }

    .frontCard:hover .retroCard {
      display: block;
    }
}
</style>
