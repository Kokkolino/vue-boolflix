<template>
  <div id="app">
    <HeaderComp/>
    <MainComp/>
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
// import axios from 'axios'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
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
