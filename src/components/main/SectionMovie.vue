<template>
    <section class="movies container">
        <h1 v-if="(globalObject.displaySectionTitle === undefined)"></h1>
        <h1 v-else-if="(globalObject.displaySectionTitle === true)">Film trovati cercando "{{globalObject.searchTextGlobal}}"</h1>
        <h1 v-else>La ricerca non ha prodotto risultati tra i film</h1>
        <ul class="row d-flex justify-content-between">
            <li class="col" v-for="movie in globalObject.movies" :key="movie.id">
                <HoverCard
                    :poster="`https://image.tmdb.org/t/p/w342${movie.poster_path}`"
                    :posterAlt="movie.original_title"
                    :title="movie.title"
                    :originalTitle="movie.original_title"
                    :originalLanguage="movie.original_language"
                    :vote="movie.vote_average"
                    :plot="movie.overview"
                    :imageFlag="existFlag(movie.original_language) ? require(`../../assets/img/flags/${movie.original_language}.png`) : require(`../../assets/img/flags/no-flag.png`)"
                />
            </li>
        </ul>
        <!-- <ul>
            <h1>Lista film</h1>
            <li v-for="movie in globalObject.movies" :key="movie.id">
                <h3>{{movie.title}}</h3>
                <ul>
                    <li>
                        <img class="poster" :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" :alt="movie.original_title">
                    </li>
                    <li>
                        <p>Titolo originale: {{movie.original_title}}</p>
                    </li>
                    <li>
                        <p>Lingua originale: {{movie.original_language}} <img class="flag" :src="existFlag(movie.original_language) ? require(`../../assets/img/flags/${movie.original_language}.png`) : require(`../../assets/img/flags/no-flag.png`)"></p>
                    </li>
                    <li>
                        <p>Voto: <span v-html="starVote(movie.vote_average)"></span></p>
                    </li>
                </ul>
            </li>
        </ul> -->
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
        existFlag(language) {
            return this.flags.includes(language);
        },

        starVote(vote) {
            let fullStar ="";
            for (let i = 0; i < Math.floor(vote / 2); i++) {
                this.fullStars = + 1;
            }
            return fullStar;
        }
    }
}
</script>

<style lang="scss" scoped>
.movies.container {

    h1 {
        text-align: center;
    }

    ul {
        list-style: none;
    }
}
</style>