<template>
    <!-- cards here -->
    <div class="flip-card element-bg">
        <div class="flip-card-inner">
            <div class="flip-card-front">
                <img v-if="showsMain2Elem.poster_path != null" :src="`https://image.tmdb.org/t/p/w342/${showsMain2Elem.poster_path}`" alt="Avatar" class="elem-img">
                <img v-else src="../../assets/Image_not_available.png" class="elem-img" alt="">
            </div>
            <div class="flip-card-back element-bg">
                <p>
                    {{showsMain2Elem.name}}
                </p>
                <p>
                    {{showsMain2Elem.original_title}}
                </p>
                <br>
                <img :src="`https://www.countryflagicons.com/FLAT/32/${(showsMain2Elem.original_language == 'en') ? 'GB' : ((showsMain2Elem.original_language == 'ja') ? 'JP' : showsMain2Elem.original_language.toUpperCase())}.png`">
                <div>
                    <div>
                        <span v-for="n in fulls" :key="`c${n}`">
                            <font-awesome-icon icon="fa-solid fa-star" />
                        </span>
                        <span v-if="this.halfs">
                            <font-awesome-icon  icon="fa-regular fa-star-half-stroke"/>
                        </span>
                        <span v-for="n in empty" :key="`d${n}`">
                            <font-awesome-icon icon="fa-regular fa-star" />
                        </span>
                    </div>
                    {{showsMain2Elem.vote_average}}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'showsComp',
        props:{
            showsMain2Elem: Object
        },
        data(){
            return{
                fulls: 0,
                halfs: false,
                empty: 5,
                decimals: (this.showsMain2Elem.vote_average / 2) % 1,
            }
        },
        methods: {
            stars(){
                this.fulls = parseInt(this.showsMain2Elem.vote_average / 2);
                this.empty += - this.fulls 
                if(this.decimals > 0.39 && this.decimals < 0.85){
                    this.halfs = true
                    this.empty--
                }
                else if (this.decimals >= 0.85) {
                    this.fulls++
                    this.empty--
                } 
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