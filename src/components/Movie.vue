<template>
    <div class="movie">
        <div>Titolo: {{ details.title }}</div>
        <div>Titolo originale: {{ details.original_title }}</div>
        <div>Lingua: {{ details.original_language }}</div>
        <div>Voto: {{ details.vote_avarage }}</div>
    </div>
</template>
<script>
export default {
    name: "MovieCard",
    props: {
        details: Object
    }
}
</script>
<style scoped>
</style>