<template>
  <header>
      <div class="container-fluid">
          <div class="row">
              <div class="col-12 col-md-2 title">
                <h1>BOOLFLIX</h1> 
              </div>
              <div class="col-12 col-md-10 search">
                <input v-model="inputSearch" type="text" placeholder="Cerca film o serie tv">
                <button @click.prevent="$emit('inputSearchFromHeader', inputSearch)">Cerca</button>
              </div>
          </div>
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
        padding: .625rem;
        background-color: black;
    }
    h1 {
        color: var(--rosso);
    }

    .search {
        text-align: right;
    }

    @media screen and (max-width: 768px) {
        .search,
        .title {
            text-align: center;
        }
    }
    
    input {
        padding: 5px;
    }
    
    button {
        background-color: var(--rosso);
        font-weight: bold;
        color: black;
        padding: 7px 14px;
        border-style: none;
        margin-left: 10px;
        border-radius: 5px;
    }

    .row {
        align-items: center;
    }

</style>