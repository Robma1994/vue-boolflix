<template>
  <div id="app">
    <Header @clickBtn='research' />
    <Main 
      :listMain = listMovies 
      :series = listSeries
    />
  </div>
</template>

<script>
import axios from 'axios'
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      listMovies: [],
      listSeries: [],
      apiNetflix: 'https://api.themoviedb.org/3/search/',
      //what: movie,tv,etc
      ApiKey:'?api_key=cccfd668f87b751c8d927b2426c90b75',
      query: '&query='
    }
  },
  methods: {
    research(writeUser) {
        axios
          .get(this.apiNetflix + 'movie' + this.ApiKey + this.query + writeUser)
          .then(res => {
            this.listGeners = res.data.results;
          })
        axios
          .get(this.apiNetflix + 'tv' + this.ApiKey + this.query + writeUser)
          .then(res => {
            this.listSeries = res.data.results;
          })
      }
    }
    
}

</script>

<style lang="scss">
@import './style/generals';
</style>
