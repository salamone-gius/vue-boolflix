<template>
  <header>
    <div class="container base-header">
      <SearchBar :inputPlaceholder="searchbarInfo.placeholder" :buttonText="searchbarInfo.button"/>
    </div>
  </header>
</template>

<script>
// import axios from 'axios';
import dataShared from '../../shared/dataShared';
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

      dataShared,

      movies: [],
    }
  },

  methods: {
    searchSomething() {

    }
  }
}
</script>

<style lang="scss" scoped>

</style>