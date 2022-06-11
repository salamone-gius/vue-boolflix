<template>
    <section class="movies container">
        <ul>
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
                        <p>Voto: {{Math.ceil(movie.vote_average)}}</p>
                    </li>
                </ul>
            </li>
        </ul>
    </section>
</template>

<script>
import globalObject from '../../shared/dataShared';

export default {
    name: 'SectionMovie',

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

        integerVote(vote) {
            return Math.ceil(vote);
        }
    }
}
</script>

<style lang="scss" scoped>
.movies.container {
    border: 2px solid yellow;

    h1 {
        text-align: center;
    }

    li{
        img.flag {
            width:1.875rem;
        }
    }
}

</style>