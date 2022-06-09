<template>
    <section class="search container">
        <SearchBar :inputPlaceholder="searchbarInfo.placeholder" :buttonText="searchbarInfo.button"/>
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
    }
}
</script>

<style lang="scss" scoped>

</style>