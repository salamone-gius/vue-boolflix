<template>
    <form class="input-group my-3" @submit.prevent="searchSomething">
        <input v-model="searchText" required :placeholder="inputPlaceholder" type="text" class="form-control" aria-label="Recipient's username" aria-describedby="button-addon2">
        <button class="btn btn-outline-secondary" type="submit" id="button-addon2">{{buttonText}}</button>
    </form>
</template>

<script>
import axios from 'axios';
import globalObject from '../../shared/dataShared';

export default {
    name: 'SearchBar',

    props: {
        buttonText: String,
        inputPlaceholder: String,
    },

    data() {
        return {
            searchText: "",

            globalObject,
        }
    },

    methods: {
        searchSomething() {
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key: '88298d08dd2155d218d8febb493ff902',
                    query: this.searchText,
                    language: 'it-IT'
                }
            }).then((response) => {
                globalObject.movies = response.data.results;
            }).catch((error) => {
                console.log(error);
            })
        },
    }
}
</script>

<style lang="scss" scoped>

</style>