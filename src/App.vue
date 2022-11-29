<template>
  <div id="app">
    <HeaderComp @headerToApp="searchMovie"/>
    <MainComp/>
  </div>
</template>

<script>

import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  Data(){
    return{
      filter: '',
      movies: null,
      shows: null
    }
  },
  methods: {
    // calling api query
    getApi(filter){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=c74eff81ff57e4d38b96c0c7d66c58a5&query=${filter}`)
      .then(response => {
        // movies
        this.movies = response.data.results
        console.log(this.movies)
      }),
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=c74eff81ff57e4d38b96c0c7d66c58a5&query=${filter}`)
      .then(response => {
        // shows
        this.shows = response.data.results
        console.log(this.shows)
      })
    

    },
    searchMovie(filtered){
      this.getApi(filtered)
    }
  },
  mounted(){
  }
}
</script>

<style lang="scss">
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    background-color: #000000;
    min-height: 100vh;
  }

  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  // bg classes
  .element-bg{
    background-color: #303030;
  }

  // color classes
  .c-white{
    color: white;
  }

  // flex classes
  .f-bw{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .f-fs{
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }

  .gap-20{
    gap: 20px;
  }
  // dimension classes
  .h-100{
    height: 100%;
  }
  
  .h-80px{
    height: 80px;
  }

  .w-75{
    width: 75%;
    margin: auto;
  }
  // cards classes
  .card{
    flex-basis: calc(100% / 5);
    height: 300px;
  }
</style>
