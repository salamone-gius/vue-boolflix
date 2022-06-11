<template>
    <section class="search container">
        <ul>
            <li v-for="movie in globalObject.movies" :key="movie.id">
                <h3>{{movie.title}}</h3>
                <ul>
                    <li>
                        <p>Titolo originale: {{movie.original_title}}</p>
                    </li>
                    <li>
                        <p>Lingua: {{movie.original_language}} <img :src="existFlag(movie.original_language) ? require(`../../assets/img/flags/${movie.original_language}.png`) : require(`../../assets/img/flags/no-flag.png`)"></p>
                    </li>
                    <li>
                        <p>Voto: {{movie.vote_average}}</p>
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
            ]
        }
    },

    methods: {
        existFlag(language) {
            return this.flags.includes(language);
        }
    }
}
</script>

<style lang="scss" scoped>
li{
    img {
        width:1.875rem;
    }
}
</style>