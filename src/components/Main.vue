<template>
  <div class="main">
      <div class="films container-fluid">
          <div class="row">
                <h2>FILMS</h2>
                <Card v-for="(film, index) in films" :key="index" :card="film" />
          </div>
      </div>
      <div class="series container-fluid">
          <div class="row">
            <h2>SERIES</h2>
            <Card v-for="(serie, index) in series" :key="index" :card="serie" />
          </div>
      </div>
  </div>
</template>

<script>
import Card from './Card.vue';
import axios from 'axios';

export default {
    name: 'Main',
    components: {
        Card
    },
    data() {
        return {
            films: [],
            series: []
        }
    },
    props: ['inputSearch'],
    watch: {
        inputSearch() {
            const apy_key = '933f816273dcac2d9bb3de85d7f0a2c6';
            const language = 'it-IT';
            // Chiamata Axios Films
            axios
            .get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key: apy_key,
                    query: this.inputSearch,
                    language: language
                }
            })
            .then((response) => {
                this.films = response.data.results   
            });
            // Chiamata Axios Series
            axios
            .get('https://api.themoviedb.org/3/search/tv', {
                params: {
                    api_key: apy_key,
                    query: this.inputSearch,
                    language: language
                }
            })
            .then((response) => {
                this.series = response.data.results
            });
        } 
    }
}
</script>

<style lang="scss" scoped>
</style>