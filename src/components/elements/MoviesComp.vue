<template>
    <!-- cards here -->
    <div class="card element-bg c-white">
        <img :src="`http://image.tmdb.org/t/p/w342/${moviesMain2Elem.backdrop_path}`" alt="">
    </div>
</template>

<script>


    export default {
        name: 'MoviesComp',
        props:{
            moviesMain2Elem: Object
        }
    }
</script>

<style lang="scss" scoped>
    h1{
        margin-bottom: 15px;
    }

    img{
        max-width: 100%;
        max-height: 100%;
    }

    span{
        background-repeat: no-repeat;
        background-size: cover;
    }
</style>