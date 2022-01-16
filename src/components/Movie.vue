<template>
    <div class="movie">
         <div>
            <img :src="(`https://image.tmdb.org/t/p/w342${details.poster_path}`)" :alt="details.poster_path">
        </div>
        <div v-if="details.title">Titolo: {{ details.title }}</div>
        <div v-else>Titolo: {{ details.name }}</div>
        <div v-if="details.original_title">Titolo originale: {{ details.original_title }}</div>
        <div v-else>Titolo originale: {{ details.original_name }}</div>
        <div class="flags">
            Lingua:
            <span v-if="pngFlag.includes(details.original_language)">
                <img :src="require(`../assets/img/${details.original_language}.png`)" :alt="details.original_language">
            </span> 
            <span v-else>{{ details.original_language }}</span>
        </div>
        <div>
            Voto: 
            <span v-for="number in 5" :key="number">
            <span v-if="number <= (Math.ceil(details.vote_average / 2))"><i class="fas fa-star"></i></span>
            <span v-else><i class="far fa-star"></i></span>
        </span>
        </div>
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