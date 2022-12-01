<template>
    <!-- cards here -->
    <div class="flip-card element-bg">
        <div class="flip-card-inner">
            <div class="flip-card-front">
                <img v-if="moviesMain2Elem.poster_path != null" :src="`https://image.tmdb.org/t/p/w342/${moviesMain2Elem.poster_path}`" alt="Avatar" class="elem-img">
                <img v-else src="../../assets/Image_not_available.png" class="elem-img" alt="">
            </div>
            <div class="flip-card-back element-bg">
                <p>
                    {{moviesMain2Elem.title}}
                </p>
                <p>
                    {{moviesMain2Elem.original_title}}
                </p>
                <br>
                <img :src="`https://www.countryflagicons.com/FLAT/32/${(moviesMain2Elem.original_language == 'en') ? 'GB' : ((moviesMain2Elem.original_language == 'ja') ? 'JP' : moviesMain2Elem.original_language.toUpperCase())}.png`">
                <div>
                    {{moviesMain2Elem.vote_average}}
                    {{stars()}}
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    export default {
        name: 'MoviesComp',
        props:{
            moviesMain2Elem: Object
        },
        data(){
            return{
                vote: '', 
                half: '',
            }
        },
        methods: {
            stars(){
                this.vote = this.moviesMain2Elem.vote_average / 2;
                this.half = this.vote % 1;
                let i= 1;
                let arr = [];
                // filled stars
                for(i; i< this.vote; i++){
                    arr.push("2")
                }
                // half stars
                if(this.half > 0.39 && this.half < 0.91){
                    arr.push("1")
                    i++
                }
                if (this.half >= 0.91) {
                    arr.push("2")
                    i++
                } else {
                    arr.push("0")
                    i++
                }
                // empty stars
                for(i; i<= 5; i++){
                    arr.push("0")
                }
                return arr
            }
        }
    }
</script>

<style lang="scss" scoped>


</style>