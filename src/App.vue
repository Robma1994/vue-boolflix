<template>
  <div id="app">
    <Header @clickBtn='research' />
    <Main :listMain = listGeners />
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
      listGeners: [],
      apiNetflix: 'https://api.themoviedb.org/3/search/movie?api_key=cccfd668f87b751c8d927b2426c90b75',
      query: '&query='
    }
  },
  created() {
    this.start()
  },
  methods: {
    start() {
      axios
            .get(this.apiNetflix + this.query + 'all')
            .then(res => {
              this.listGeners = res.data.results;
            })
    },
    research(writeUser) {
        axios
            .get(this.apiNetflix + this.query + writeUser)
            .then(res => {
              this.listGeners = res.data.results;
            })
      }
    }
    
}

</script>

<style lang="scss">
@import './style/generals';

</style>
