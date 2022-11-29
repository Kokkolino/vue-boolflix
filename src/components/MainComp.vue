<template>
    <div class="w-75">
        <MoviesComp/>
        <ShowsComp/>
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
        }
    }
</script>

<style lang="scss" scoped>
    div{
        margin-top: 25px;
    }
</style>