<template>
<div class="col-2 px-3 py-3">
    <img class="img-fluid" :src='`http://image.tmdb.org/t/p/w500/${propsFilm.poster_path}`' alt="">
    <div class="pt-2 ps-1"><h5>Film</h5></div>
    <div class="pb-1 ps-1"><h6 class="title">{{propsFilm.original_title}}</h6></div>
    <div class="pb-1 ps-1"><span>Vote: {{propsFilm.vote_average}}</span></div>
    <div class="lingua ps-1"><span>Language: </span><span>{{flagFunction()}}</span></div>
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
background-color: white;
}
.lingua {
    background-color: red;
}
.title {
}
</style>