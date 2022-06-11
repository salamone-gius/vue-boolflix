<template>
  <header>
    <div class="container base-header">
      <SearchBar v-model="searchText" :inputPlaceholder="searchbarInfo.placeholder" :buttonText="searchbarInfo.button"/>
    </div>
  </header>
</template>

<script>
// import axios from 'axios';
import SearchBar from '../commons/SearchBar.vue';

export default {
    name : 'BaseHeader',

    components: {
      SearchBar,
    },

    data() {
        return {
            searchbarInfo: {
                placeholder: "Search movie, tv series and more",
                button: "Search",
            },

            searchText: "",

            movies: [],
        }
    },
}
</script>

<style lang="scss" scoped>

</style>