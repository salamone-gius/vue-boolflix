<template>
    <section class="search container">
        <ul>
            <li v-for="movie in globalObject.movies" :key="movie.id">
                <h3>{{movie.title}}</h3>
                <ul>
                    <li>Titolo originale: {{movie.original_title}}</li>
                    <li>Lingua: {{movie.original_language}}</li>
                    <li>Voto: {{movie.vote_average}}</li>
                </ul>
            </li>
        </ul>
    </section>
</template>

<script>
import globalObject from '../../shared/dataShared';

export default {
    name: 'SectionSearch',

    data() {
        return {
            globalObject,
        }
    }
}
</script>

<style lang="scss" scoped>

</style>