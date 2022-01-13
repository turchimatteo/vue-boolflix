<template>
    <main>
        <h2>Film:</h2>
        <Movie v-for="movie in movieList" :key="movie.id" :details="movie"/>
    </main>
</template>
<script>
import Movie from "./Movie.vue"

export default {
    name: "Main",
    components: {
        Movie
    },
    props: {
        movieList: Array
    },
}
</script>