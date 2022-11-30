<template>
    <!-- cards here -->
    <div class="card element-bg c-white">
        <img :src="`http://image.tmdb.org/t/p/w342/${showsMain2Elem.backdrop_path}`" alt="">
    </div>
</template>

<script>


    export default {
        name: 'ShowsComp',
        props:{
            showsMain2Elem: Object
        },
        methods: {
            check(){
                console.log(this.showsLastTrip)
            }
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