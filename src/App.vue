<template>
  <div id="app">
    <Header @inputSearchFromHeader="inputSearchInApp" />
    <Films :inputSearch="inputSearch" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Films from './components/Films.vue'

export default {
  name: 'App',
  components: {
    Header,
    Films
  },
  data() {
    return {
      inputSearch: ""
    }
  },
  methods: {
    inputSearchInApp(inputSearch) {
      this.inputSearch = inputSearch
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/common.scss';

</style>
