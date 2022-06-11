<template>
  <header>
    <div class="container base-header">
      <SearchBar :inputPlaceholder="searchbarInfo.placeholder" :buttonText="searchbarInfo.button"/>
    </div>
  </header>
</template>

<script>
import SearchBar from '../commons/SearchBar.vue';

export default {
  name : 'BaseHeader',

  components: {
    SearchBar,
  },

  data() {
    return {
      searchbarInfo: {
        placeholder: "Cerca film, serie TV e altro",
        button: "Cerca",
      },
    }
  },
}
</script>

<style lang="scss" scoped>

</style>