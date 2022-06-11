<template>
    <section class="series container">
        <ul>
            <h1>Lista serie TV</h1>
            <li v-for="serie in globalObject.series" :key="serie.id">
                <h3>{{serie.name}}</h3>
                <ul>
                    <li>
                        <img class="poster" :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" :alt="serie.original_name">
                    </li>
                    <li>
                        <p>Titolo originale: {{serie.original_name}}</p>
                    </li>
                    <li>
                        <p>Lingua originale: {{serie.original_language}} <img class="flag" :src="existFlag(serie.original_language) ? require(`../../assets/img/flags/${serie.original_language}.png`) : require(`../../assets/img/flags/no-flag.png`)"></p>
                    </li>
                    <li>
                        <p>Voto: {{Math.ceil(serie.vote_average)}}</p>
                    </li>
                </ul>
            </li>
        </ul>
    </section>
</template>

<script>
import globalObject from '../../shared/dataShared';

export default {
    name: 'SectionTvSeries',

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