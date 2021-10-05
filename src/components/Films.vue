<template>
  <div class="films">
      <ul>
          <li v-for="(film, index) in films" :key="index">{{film.original_title}}</li>
      </ul>
      <Film />
  </div>
</template>

<script>
import Film from './Film.vue'
import axios from 'axios';

export default {
    name: 'Films',
    components: {
        Film
    },
    data() {
        return {
            films: []
        }
    },
    props: {
        inputSearch: String
    },
    watch: {
        prova() {
            axios.get('https://api.themoviedb.org/3/search/movie', {
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