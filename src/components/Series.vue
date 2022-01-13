<template>
    <div class="series">
        <div>Titolo: {{ details.name }}</div>
        <div>Titolo originale: {{ details.original_name }}</div>
        <div>
            Lingua:
            <span v-if="pngFlag.includes(details.original_language)">
                <img class="flags" :src="require(`../assets/img/${details.original_language}.png`)" :alt="details.original_language">
            </span> 
            <span v-else>{{ details.original_language }}</span>
        </div>
        <div>Voto: {{ details.vote_average }}</div>
    </div>
</template>
<script>
export default {
    name: "Series",
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
.series {
    margin: 20px;
    border: 1px solid black;
    width: 342px;
    display: flex;
    flex-direction: column;
    flex-shrink: 0;
    img {
        width: 40px;
    }
}
</style>