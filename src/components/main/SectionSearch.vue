<template>
    <section class="search container">
        <SearchBar @searching="searchSomething" :inputPlaceholder="searchbarInfo.placeholder" :buttonText="searchbarInfo.button"/>
    </section>
</template>

<script>
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
    }
}
</script>

<style lang="scss" scoped>

</style>