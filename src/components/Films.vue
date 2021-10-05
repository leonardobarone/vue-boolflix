<template>
  <div class="films">
      <Film />
  </div>
</template>

<script>
import Film from './Film.vue'

export default {
    name: 'Films',
    components: {
        Film
    },
    props: {
        inputSearch: String
    }
}
</script>

<style lang="scss" scoped>

</style>