<template>
    <main class="row overflow-auto row pt-5">
        <FilmsList v-for="(element, index) in moviesUtenteMain[0].movie[0]" :key = "index" :propsFilm="element"/>
        <SeriesList v-for="(element, index) in moviesUtenteMain[1].series[0]" :key = "index" :propsSeries="element"/>
    </main>
</template>

<script>
import FilmsList from './FilmsList.vue'
import SeriesList from './SeriesList.vue'




export default {
name: "MainComp",
props: {
moviesUtenteMain: Object
},
components: {
    FilmsList,
    SeriesList
}
}
</script>

<style lang="scss" scoped>
main {
height: 90%;
}
</style>

