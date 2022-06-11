<template>
    <section class="search container">
        <!-- <ul>
            <li v-for="movie in movies" :key="movie.id">
                <h3>{{movie.title}}</h3>
                <ul>
                    <li>Titolo originale: {{movie.original_title}}</li>
                    <li>Lingua: {{movie.original_language}}</li>
                    <li>Voto: {{movie.popularity}}</li>
                </ul>
            </li>
        </ul> -->
    </section>
</template>

<script>
export default {
    name: 'SectionSearch',

    methods: {
        // searchSomething() {
        //     axios.get('https://api.themoviedb.org/3/search/movie', {
        //         params: {
        //             api_key: '88298d08dd2155d218d8febb493ff902',
        //             // testo da cercare (dinamico con v-model)
        //             query: this.searchText,
        //             language: 'it-IT'
        //         }
        //     }).then((response) => {
        //         console.log("response.data.results = ", response.data.results);
        //         this.movies = response.data.results;
        //         console.log("array movies = ", this.movies);
        //     }).catch((error) => {
        //         console.log(error);
        //     })
        // }
    },
}
</script>

<style lang="scss" scoped>

</style>