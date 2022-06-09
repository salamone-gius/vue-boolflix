<template>
    <section class="search container">
        <!-- <SearchBar v-model="cerca" @searching="searchSomething" :inputPlaceholder="searchbarInfo.placeholder" :buttonText="searchbarInfo.button"/> -->
        <form class="input-group my-3" @submit.prevent="searchSomething">
            <input v-model="searchText" placeholder="Search" type="text" class="form-control" aria-label="Search" aria-describedby="button-addon2">
            <button class="btn btn-outline-secondary" type="button" id="button-addon2">Search</button>
        </form>

        <ul>
            <li v-for="movie in movies" :key="movie.id">{{movie.title}}</li>
        </ul>
    </section>
</template>

<script>
import axios from 'axios';
// import SearchBar from '../commons/SearchBar.vue';

export default {
    name: 'SectionSearch',

    components: {
        // SearchBar,
    },

    data() {
        return {
            // searchbarInfo: {
            //     placeholder: "Search movie, tv series and more",
            //     button: "Search",
            // },

            searchText: "",

            movies: [],
        }
    },

    methods: {
        searchSomething() {
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key: '88298d08dd2155d218d8febb493ff902',
                    // testo da cercare (dinamico con v-model)
                    query: this.searchText,
                    language: 'it-IT'
                }
            }).then((response) => {
                console.log("response.data.results = ", response.data.results);
                this.movies = response.data.results;
                console.log("array movies = ", this.movies);
            }).catch((error) => {
                console.log(error);
            })
        }
    },
}
</script>

<style lang="scss" scoped>

</style>