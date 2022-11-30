<template>
    <!-- cards here -->
    <div class="card element-bg">
        <div class="flip-card-inner">
            <div class="flip-card-front">
                <img class="elem-img" :src="`https://image.tmdb.org/t/p/w342/${showsMain2Elem.poster_path}`" alt="Avatar">
            </div>
            <div class="flip-card-back element-bg">
                <h1>John Doe</h1> 
                <p>Architect & Engineer</p> 
                <p>We love that guy</p>
            </div>
        </div>
    </div>
</template>

<script>


    export default {
        name: 'ShowsComp',
        props:{
            showsMain2Elem: Object
        },
    }
</script>

<style lang="scss" scoped>

</style>