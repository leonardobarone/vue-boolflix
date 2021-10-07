<template>
    <div class="card col-12 col-md-2 no-gutters">
            <div class="poster_path">
                <img :src="`https://image.tmdb.org/t/p/w200${card.poster_path}`" alt="">
            </div>
            <div class="title">
                {{card.title ? card.title : card.name}}
            </div>
            <div class="original_title">
                {{card.original_title || card.original_name}}
            </div>
            <div class="original_language">
                <img v-if="flags.includes(card.original_language)" :src="require(`../assets/img/flag/${card.original_language}.png`)" alt="">
                <img v-else :src="require(`../assets/img/flag/peace.png`)" alt="">
            </div>
            <div class="vote_average" v-for="(number, index) in 5" :key="index">

                    <i v-if="index <= Math.floor(card.vote_average / 2)" class="fas fa-star"></i>
                    <i v-else class="far fa-star" :key="index"></i>
          
                    <!-- <i class="far fa-star"></i>
                    <i class="fas fa-star"></i> -->
            </div>
        </div>

</template>

<script>


export default {
    name: 'Card',
    props: {
        card: Object
    },
    data() {
        return {
            flags: ['en', 'fr', 'it']
        }
    }
}
</script>

<style lang="scss" scoped>
// @import '@fortawesome/fontawesome-free/js/all.js';
@import '~@fortawesome/fontawesome-free/css/all.css';
// @import '~@fortawesome/fontawesome-free/scss/fontawesome';

    .card {
        border: 1px solid white;
        background-color: var(--nero);
        .original_language img {
            width: 15px;
        }
    }

    .poster_path {
        height: 300px;
    }


    .poster_path img{
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
    }

    
</style>