<template>
  <div id="app">
    <Header @inputSearchFromHeader="inputSearchInApp" />
    <Main :inputSearch="inputSearch" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
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
