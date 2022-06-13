<template>
    <section class="series container">
        <h1 v-if="(globalObject.displaySectionTitle === undefined)"></h1>
        <h1 v-else-if="(globalObject.displaySectionTitle === true)">Serie TV trovate cercando "{{globalObject.searchTextGlobal}}"</h1>
        <h1 v-else>La ricerca non ha prodotto risultati tra le serie TV</h1>
        <ul class="row d-flex">
            <li class="col-12 col-sm-12 col-md-6 col-lg-4 col-xl-3" v-for="serie in globalObject.series" :key="serie.id">
                <HoverCard
                    :poster="posterShow(serie.poster_path)"
                    :posterAlt="serie.original_name"
                    :title="serie.name"
                    :originalTitle="serie.original_name"
                    :originalLanguage="serie.original_language"
                    :vote="serie.vote_average"
                    :plot="serie.overview"
                    :imageFlag="flagShow(serie.original_language)"
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
        posterShow(path) {
            if (path === null) {
                return require('../../assets/img/no-poster-img.jpg');
            } else {
                return `https://image.tmdb.org/t/p/w342${path}`;
            }
        },

        flagShow(path) {
            if (this.flags.includes(path)) {
                return require(`../../assets/img/flags/${path}.png`);
            } else {
                return require(`../../assets/img/flags/no-flag.png`);
            }
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