<template>
    <section class="movies container">
        <h1>Lista film</h1>
        <ul class="row d-flex justify-content-between">
            <li class="col" v-for="movie in globalObject.movies" :key="movie.id">
                <HoverCard
                    :poster="`https://image.tmdb.org/t/p/w342${movie.poster_path}`"
                    :posterAlt="movie.original_title"
                    :title="movie.title"
                    :originalTitle="movie.original_title"
                    :originalLanguage="movie.original_language"
                    :vote="starVote(movie.vote_average)"
                    :plot="movie.overview"
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
            for (let i = 0; i < Math.ceil(vote / 2); i++) {
                fullStar += '<i class="fab fa-solid fa-star"></i>';
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

    li{
        img.flag {
            width:1.875rem;
        }
    }
}

</style>