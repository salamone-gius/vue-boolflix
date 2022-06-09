<template>
    <section class="search container">
        <SearchBar/>
    </section>
</template>

<script>
import SearchBar from '../commons/SearchBar.vue';

export default {
    name: 'SectionSearch',

    components: {
        SearchBar,
    }
}
</script>

<style lang="scss" scoped>

</style>