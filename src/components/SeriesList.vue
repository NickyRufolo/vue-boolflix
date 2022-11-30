<template>
<div class="col-2 px-3 py-3">
    <img class="img-fluid" :src='`http://image.tmdb.org/t/p/w500/${propsSeries.poster_path}`'>
    <div class="d-none">
    <div class="pt-2 ps-1"><h5>Serie</h5></div>
    <div class="pb-1 ps-1"><h6>Title: {{propsSeries.name}}</h6></div>
    <div class="pb-1 ps-1"><strong>Vote: </strong>
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsSeries.vote_average / 2 > 0 || propsSeries.vote_average == '')?'star':'star-empty'"/>
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsSeries.vote_average / 2 > 1)?'star':'star-empty'" />
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsSeries.vote_average / 2 > 2)?'star':'star-empty'" />
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsSeries.vote_average / 2 > 3)?'star':'star-empty'" />
        <font-awesome-icon icon="fa-solid fa-star" v-bind:class="(propsSeries.vote_average / 2 > 4)?'star':'star-empty'" />
    </div>
    <div class="lingua ps-1"><span>Country: {{flagFunction()}}</span></div>
</div>
</div>
</template>
    
<script>
    export default {
    name: "SeriesList",
    props: {
        propsSeries : Object
    },
    data(){
        return{
            flag: ""
        }
    },
    methods: {
        flagFunction(){
            if (this.propsSeries.original_language == `it`){
                return this.flag = '🇮🇹'
            }else if(this.propsSeries.original_language == `en`){
                return this.flag = '🇬🇧'
            }else if(this.propsSeries.original_language == "es"){
                return this.flag = "🇪🇸"
            }else if(this.propsSeries.original_language == `ja`){
                return this.flag = "🇯🇵"
            }else if(this.propsSeries.original_language == "fr"){
                return this.flag = "🇫🇷"
            }
        }
    }
    }
    </script>
    
<style lang="scss" scoped>
    .pb-1 {
    background-color: white;
    }
    .lingua {
        background-color: red;
    }
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