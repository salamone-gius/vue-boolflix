<template>
    <section class="series container">
        <h1 v-if="(globalObject.displaySectionTitle === undefined)"></h1>
        <h1 v-else-if="(globalObject.displaySectionTitle === true)">Serie TV trovate cercando "{{globalObject.searchTextGlobal}}"</h1>
        <h1 v-else>La ricerca non ha prodotto risultati tra le serie TV</h1>
        <ul class="row d-flex justify-content-between">
            <li class="col" v-for="serie in globalObject.series" :key="serie.id">
                <HoverCard
                    :poster="`https://image.tmdb.org/t/p/w342${serie.poster_path}`"
                    :posterAlt="serie.original_name"
                    :title="serie.name"
                    :originalTitle="serie.original_name"
                    :originalLanguage="serie.original_language"
                    :vote="serie.vote_average"
                    :plot="serie.overview"
                    :imageFlag="existFlag(serie.original_language) ? require(`../../assets/img/flags/${serie.original_language}.png`) : require(`../../assets/img/flags/no-flag.png`)"
                />
            </li>
        </ul>
    </section>
</template>

<script>
import globalObject from '../../shared/dataShared';
import HoverCard from '../commons/HoverCard.vue';

export default {
    name: 'SectionTvSeries',

    components: {
        HoverCard,
    },

    data() {
        return {
            globalObject,

            flags: [
                "en",
                "it",
                "es",
                "de",
                "fr",
            ],
        }
    },

    methods: {
        existFlag(language) {
            return this.flags.includes(language);
        },
    }
}
</script>

<style lang="scss" scoped>
.series.container {

    h1 {
        text-align: center;
        color: var(--secondary-color);
    }

    ul {
        list-style: none;
    }
}
</style>