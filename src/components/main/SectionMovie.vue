<template>
    <section class="movies container">
        <h1 v-if="(globalObject.displaySectionTitle === undefined)"></h1>
        <h1 v-else-if="(globalObject.displaySectionTitle === true)">Film trovati cercando "{{globalObject.searchTextGlobal}}"</h1>
        <h1 v-else>La ricerca non ha prodotto risultati tra i film</h1>
        <ul class="row d-flex justify-content-between">
            <li class="col" v-for="movie in globalObject.movies" :key="movie.id">
                <HoverCard
                    :poster="posterShow(movie.poster_path)"
                    :posterAlt="movie.original_title"
                    :title="movie.title"
                    :originalTitle="movie.original_title"
                    :originalLanguage="movie.original_language"
                    :vote="movie.vote_average"
                    :plot="movie.overview"
                    :imageFlag="flagShow(movie.original_language)"
                />
            </li>
        </ul>
    </section>
</template>

<script>
import globalObject from '../../shared/dataShared';
import HoverCard from '../commons/HoverCard.vue';

export default {
    name: 'SectionMovie',

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
        flagShow(language) {
            if (this.flags.includes(language)) {
                return require(`../../assets/img/flags/${language}.png`);
            } else {
                return require(`../../assets/img/flags/no-flag.png`);
            }
        },

        posterShow(path) {
            if (path === null) {
                return require('../../assets/img/no-poster-img.jpg');
            } else {
                return `https://image.tmdb.org/t/p/w342${path}`;
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.movies.container {

    h1 {
        text-align: center;
        color: var(--secondary-color);
    }

    ul {
        list-style: none;
    }
}
</style>