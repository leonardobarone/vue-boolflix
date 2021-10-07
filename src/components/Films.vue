<template>
  <div class="films">
        <Card v-for="(film, index) in films" :key="index" :card="film" />
  </div>
</template>

<script>
import Card from './Card.vue';
import axios from 'axios';

export default {
    name: 'Films',
    components: {
        Card
    },
    data() {
        return {
            films: []
        }
    },
    props: ['inputSearch'],
    watch: {
        inputSearch() {
            axios
            .get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key: '933f816273dcac2d9bb3de85d7f0a2c6',
                    query: this.inputSearch,
                    language: 'it-IT'
                }
            })
            .then((response) => {
                this.films = response.data.results
              
            });
        } 
    }
}
</script>

<style lang="scss" scoped>
</style>