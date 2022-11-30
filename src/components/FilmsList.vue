<template>
<div class="col-2 px-3 py-3">
    <img class="img-fluid" :src='`http://image.tmdb.org/t/p/w500/${propsFilm.poster_path}`' alt="">
    <div class="d-none">
    <div class="Film pt-2 ps-1"><h5>Film</h5></div>
    <div class="title pb-1 ps-1"><h6 class="title">{{propsFilm.original_title}}</h6></div>
    <div class="Vote pb-1 ps-1"><strong>Vote: </strong>
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsFilm.vote_average / 2 > 0 || propsFilm.vote_average == '')?'star':'star-empty'"/>
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsFilm.voto_avarage / 2 > 1)?'star':'star-empty'"/>
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsFilm.voto_avarage / 2 > 2)? 'star' : 'star-empty'"/>
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsFilm.voto_avarage / 2 > 3)? 'star': 'star-empty'"/>
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsFilm.voto_avarage / 2 > 4)? 'star': 'star-empty'"/>
    </div>
    <div class="lingua ps-1"><span>Country: </span><span>{{flagFunction()}}</span></div>
    <div class="title pb-1 ps-1"><p class="overview">{{propsFilm.overview}}</p></div>
</div>
</div>
</template>

<script>
export default {
name: "FilmsList",
props: {
    propsFilm : Object
},
data(){
    return{
        flag: ""
    }
},
methods: {
    flagFunction(){
        if (this.propsFilm.original_language == `it`){
            return this.flag = '🇮🇹'
        }else if(this.propsFilm.original_language == `en`){
            return this.flag = '🇬🇧'
        }else if(this.propsFilm.original_language == "es"){
            return this.flag = "🇪🇸"
        }else if(this.propsFilm.original_language == `ja`){
            return this.flag = "🇯🇵"
        }else if(this.propsFilm.original_language == "fr"){
            return this.flag = "🇫🇷"
        }
    }
}
}
</script>

<style lang="scss" scoped>
.pb-1 {
    color: white
}
.lingua {
color:white}
.star {
    color:gold
    }

    .star-empty {
        color:grey
    }
    .col-2 {
    &:hover{
        border: 1px solid white;
    
    img {
        display: none;
    }
    .d-none{
    display: block !important;
    }
    .overview{
        height:170px;
        overflow-y: auto !important;
    }
}}
</style>