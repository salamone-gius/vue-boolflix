<template>
  <main>
      <SectionMovie/>
      <SectionTvSeries/>
  </main>
</template>

<script>
import SectionMovie from './SectionMovie.vue';
import SectionTvSeries from './SectionTvSeries.vue';

export default {
    name: 'BaseMain',

    components: {
        SectionMovie,
        SectionTvSeries,
    }
}
</script>

<style lang="scss" scoped>

</style>