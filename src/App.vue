<template>
  <div id="app">
    <BaseHeader/>
    <BaseMain/>
  </div>
</template>

<script>
import BaseHeader from './components/header/BaseHeader.vue';
import BaseMain from './components/main/BaseMain.vue';

export default {
  name: 'App',
  components: {
    BaseHeader,
    BaseMain,
  }
}
</script>

<style lang="scss">
@import './assets/style/global.scss';
@import'~bootstrap/dist/css/bootstrap.css';
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@400;700&display=swap');

body {
  background-color: var(--quaternary-color);
}
</style>
