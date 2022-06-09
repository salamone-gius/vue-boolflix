<template>
    <section class="search container">
        <SearchBar @searching="searchSomething" :inputPlaceholder="searchbarInfo.placeholder" :buttonText="searchbarInfo.button"/>
    </section>
</template>

<script>
import axios from 'axios';
import SearchBar from '../commons/SearchBar.vue';

export default {
    name: 'SectionSearch',

    components: {
        SearchBar,
    },

    data() {
        return {
            searchbarInfo: {
                placeholder: "Search movie, tv series and more",
                button: "Search",
            }
        }
    },

    methods: {
        searchSomething(searchThis) {
            console.log(searchThis);
        }
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
            console.log(response.data.results);
        }).catch((error) => {
            console.log(error);
        })
    }
}
</script>

<style lang="scss" scoped>

</style>