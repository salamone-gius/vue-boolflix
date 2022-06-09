<template>
    <section class="search container">
        <!-- <SearchBar v-model="cerca" @searching="searchSomething" :inputPlaceholder="searchbarInfo.placeholder" :buttonText="searchbarInfo.button"/> -->
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

            cerca: "",

            movies: [],
        }
    },

    methods: {
        // searchSomething(searchThis) {
        //     console.log(searchThis);
    },
    
    created() {
        axios.get('https://api.themoviedb.org/3/search/movie', {
            params: {
                api_key: '88298d08dd2155d218d8febb493ff902',
                // testo da cercare (dinamico con v-model)
                query: 'ritorno',
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
}
</script>

<style lang="scss" scoped>

</style>