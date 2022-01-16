<template>
    <main>
        <h2>Film:</h2>
        <div class="movies">
            <Movie v-for="movie in movieList" :key="movie.id" :details="movie"/>
        </div>
        <h2>Serie:</h2>
        <div class="series">
            <Movie v-for="series in seriesList" :key="series.id" :details="series"/>
        </div>
    </main>
</template>
<script>
import Movie from "./Movie.vue"
/* import Series from "./Series.vue" */

export default {
    name: "Main",
    components: {
        Movie,
        /* Series */
    },
    props: {
        movieList: Array,
        seriesList: Array
    },
}
</script>
<style scoped>
.movies {
    display: flex;
    flex-direction: row;
}
.series {
    display: flex;
    flex-direction: row;
}
</style>