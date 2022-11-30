<template>
    <!-- cards here -->
    <div class="card element-bg">
        <div class="flip-card-inner">
            <div class="flip-card-front">
                <img v-if="moviesMain2Elem.poster_path != null" class="elem-img" :src="`https://image.tmdb.org/t/p/w342/${moviesMain2Elem.poster_path}`" alt="Avatar">
                <img v-else class="elem-img" src="../../assets/Image_not_available.png" alt="">
            </div>
            <div class="flip-card-back element-bg">
                <div class="word-break">
                    {{`${moviesMain2Elem.title}`}} 
                    {{`${moviesMain2Elem.original_title}`}} 
                </div>
                <p>{{moviesMain2Elem.original_language}}</p>
                <p>{{moviesMain2Elem.vote_average}}</p>
            </div>
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


</style>