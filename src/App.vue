<template>
  <div id="app">
    <HeaderComp @headerToApp="searchMovie"/>
    <MainComp :moviesApp2Main="moviesArray" :showsApp2Main="showsArray"/>
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
  data(){
    return{
      moviesArray: [],
      showsArray: []
    }
  },
  methods: {
    // calling api query
    getApi(filter){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=c74eff81ff57e4d38b96c0c7d66c58a5&query=${filter}`)
      .then(response => {
        // movies
        this.moviesArray = response.data.results
      }),
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=c74eff81ff57e4d38b96c0c7d66c58a5&query=${filter}`)
      .then(response => {
        // shows
        this.showsArray = response.data.results
      })
    

    },
    // emit
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
    width: 329px;
    min-height: 193px;
    padding: 5px;
    display: inline-block;
    margin: 0 10px;
  }
  //Scroll classes
  .scroll{
    padding: 5px;
    width: 100%;
    overflow-x: auto;
    white-space: nowrap;
  }

  div.scrollmenu span {
  display: inline-block;
  color: white;
  text-align: center;
  padding: 14px;
}
</style>
