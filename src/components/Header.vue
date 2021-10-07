<template>
  <header>
      <h1>BOOLFLIX</h1>
      <div class="search">
          <input v-model="inputSearch" type="text">
          <button @click.prevent="$emit('inputSearchFromHeader', inputSearch)">Cerca</button>
      </div>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            inputSearch: ""
        }
    }
}
</script>

<style scoped lang="scss">
    header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: .625rem;
        border: 1px solid black;
    }
</style>