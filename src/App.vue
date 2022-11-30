<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <HeaderComp @emitSearch="findMovies"/>
    <MainComp :moviesUtenteMain="inputUtente"/>
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import axios from "axios"
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data(){
return {
  inputUtente: [
    {
      movie: []  
    },
    {
      series: []
    }
  ]
}
  },
  methods: {
    // film
    findMovies(param){
    axios.get(`https://api.themoviedb.org/3/search/movie?api_key=ba184a7155c350f53efb2492c0638e81&language=en-US&query=`+param+`&page=1&include_adult=true`)
    .then((response)=>{
      this.inputUtente[0].movie = [] //lo svuoto ogni volta che ricevo un nuovo input
      this.inputUtente[0].movie.push(response.data.results) //pusho nella posizione 0
    }),

    //serie
    axios.get(`https://api.themoviedb.org/3/search/tv?api_key=ba184a7155c350f53efb2492c0638e81&language=en-US&query=`+param+`&page=1&include_adult=true`)
    .then((response)=>{
      this.inputUtente[1].series = [] //lo svuoto ogni volta che ricevo un nuovo input
      this.inputUtente[1].series.push(response.data.results) //pusho nella posizione 1
    })
  }
}}

</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: black;
  height: 100vh;
}
</style>
