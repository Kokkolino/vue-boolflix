<template>
  <div class="element-bg">
    <nav class="f-bw h-100">
      <img src="../assets/logo.png" alt="logo" class="h-100">
      <input type="text" placeholder="Cerca un film">
      <i class="fa-solid fa-user h-100"></i>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'HeaderComp',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  div{
    height: 100px;
  }

  nav{
    padding: 15px;
  }

  input{
    padding: 5px;
    border-radius: 10px;
    border: none;
  }
</style>
