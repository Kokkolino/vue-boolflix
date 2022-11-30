<template>
    <div class="w-75">
        <h1>Movies</h1>
        <!-- movies -->
        <div class="scroll">
            <MoviesComp v-for="(element, index) in moviesApp2Main" 
            :moviesMain2Elem="element" 
            :key="index"/>
        </div>
        <!-- tv shows -->
        <h1>Shows</h1>
        <div class="scroll">
            <ShowsComp v-for="(element, index) in showsApp2Main" 
            :showsMain2Elem="element" 
            :key="index"/>
        </div>
    </div>
</template>

<script>
import MoviesComp from './elements/MoviesComp.vue'
import ShowsComp from './elements/ShowsComp.vue'
    export default {
        name: 'MainComp',
        components: {
            MoviesComp,
            ShowsComp
        },
        props:{
            moviesApp2Main: Array,
            showsApp2Main: Array
        },
    }
</script>

<style lang="scss" scoped>
    div{
        color: white;
    }

    h1{
        margin-top: 40px;
    }


</style>