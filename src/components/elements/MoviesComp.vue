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
                    <div>
                        <span v-for="n in fulls" :key="`a${n}`">
                            <font-awesome-icon icon="fa-solid fa-star" />
                        </span>
                        <span v-if="this.halfs">
                            <font-awesome-icon  icon="fa-regular fa-star-half-stroke"/>
                        </span>
                        <span v-for="n in empty" :key="`b${n}`">
                            <font-awesome-icon icon="fa-regular fa-star" />
                        </span>
                    </div>
                    {{moviesMain2Elem.vote_average}}
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
                fulls: 0,
                halfs: false,
                empty: 5,
                decimals: (this.moviesMain2Elem.vote_average / 2) % 1,
            }
        },
        methods: {
            stars(){
                this.fulls = parseInt(this.moviesMain2Elem.vote_average / 2);
                this.empty += - this.fulls 
                if(this.decimals > 0.39 && this.decimals < 0.85){
                    this.halfs = true
                    this.empty--
                }
                else if (this.decimals >= 0.85) {
                    this.fulls++
                    this.empty--
                } 
                console.log(this.decimals)
                return               
            }
        },
        mounted(){
            this.stars()
        }

    }
</script>

<style lang="scss" scoped>


</style>