<template>
  <div class="element-bg">
    <nav class="f-bw h-100">
      <!-- logo -->
      <img src="../assets/logo.png" alt="logo" class="h-100">
      <!-- input -->
      <input type="text" placeholder="Cerca un film"
       v-model="searchInput"
       @keyup.enter="$emit('headerToApp', searchInput)">
       <!-- user -->
      <span>
        
      </span>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'HeaderComp',
  data(){
    return {
      searchInput: ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  div{
    height: 80px;
  }

  nav{
    padding: 15px;
  }

  input{
    padding: 5px;
    border-radius: 10px;
    border: none;
  }

  span{
    cursor: pointer;
    padding: 12px;
    border: 1px solid black;
    border-radius: 50%;
    *{
      height: 40px;
    }
  }
</style>
