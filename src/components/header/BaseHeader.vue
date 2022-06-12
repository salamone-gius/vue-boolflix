<template>
  <header>
    <nav class="container-flex px-3 base-header d-flex justify-content-between align-items-center">
      <div class="logo">
        <LogoBox :imageClass="logoInfo.imageClass" :imageSrc="logoInfo.imageSrc" imageAlt="imageAlt"/>
      </div>
      <div class="searchbar">
        <SearchBar :inputPlaceholder="searchbarInfo.placeholder" :buttonText="searchbarInfo.button"/>
      </div>
      <div class="ghost"></div>
    </nav>
  </header>
</template>

<script>
import SearchBar from '../commons/SearchBar.vue';
import LogoBox from '../commons/LogoBox.vue';

export default {
  name : 'BaseHeader',

  components: {
    SearchBar,
    LogoBox,
  },

  data() {
    return {
      searchbarInfo: {
        placeholder: "Cerca film, serie TV e altro",
        button: "Cerca",
      },
      logoInfo: {
        imageSrc: require('../../assets/img/boolflix-logo.png'),
        imageAlt: "Boolflix",
        imageClass: "logo-img",
      }
    }
  },
}
</script>

<style lang="scss" scoped>
header {
  padding: var(--container-padding);

  .searchbar {
    width: 31rem;
    // margin-left: 15rem;
  }

  .ghost {
    width: 13.5rem;
  }
}

// .logo-img {
//   width: 12.5rem;
// }

</style>