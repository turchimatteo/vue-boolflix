<template>
    <div class="movie">
         <div>
            <img :src="(`https://image.tmdb.org/t/p/w342${details.poster_path}`)" :alt="details.poster_path">
        </div>
        <div>Titolo: {{ details.title }}</div>
        <div>Titolo originale: {{ details.original_title }}</div>
        <div class="flags">
            Lingua:
            <span v-if="pngFlag.includes(details.original_language)">
                <img :src="require(`../assets/img/${details.original_language}.png`)" :alt="details.original_language">
            </span> 
            <span v-else>{{ details.original_language }}</span>
        </div>
        <div>Voto: {{ details.vote_average }}</div>
    </div>
</template>
<script>
export default {
    name: "Movie",
    data: function() {
        return {
            pngFlag: ['it', 'en']
        };
    },
    props: {
        details: Object
    }
}
</script>
<style scoped lang="scss">
.movie {
    margin: 20px;
    border: 1px solid black;
    width: 342px;
    display: flex;
    flex-direction: column;
    flex-shrink: 0;
    .flags img {
        width: 40px;
    }
}
</style>