<template>
    <!-- cards here -->
    <div class="card element-bg c-white">
        <div class="bg-image">
            <img v-if="(moviesMain2Elem.backdrop_path != null)" :src="`http://image.tmdb.org/t/p/w342/${moviesMain2Elem.backdrop_path}`" alt="">
            <img v-else src="../../assets/Image_not_available.png" alt="">
        </div>
        <div class="info">
            <h2>ciao</h2>
        </div>
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

    .info{
        width: 324px;
        height: 188px;
        display: none;
    }

    .bg-image{
        width: 100%;
        height: 100%;
    }
    .card:hover{
        .bg-image{
            display: none;
        }
        .info{
            display: block;
        }
    }
</style>