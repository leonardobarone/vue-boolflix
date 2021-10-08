<template>
    <div class="card col-12 col-md-3 no-gutters">
           
        <div class="poster_path">
            
                <img v-if="card.poster_path" :src="`https://image.tmdb.org/t/p/w342${card.poster_path}`" alt="">
                <img v-else :src="require(`../assets/img/poster.jpg`)" alt="">
           
       
        <div class="description">
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
                    <i v-else class="far fa-star"></i>
            </div>
        </div>
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

    .poster_path {
        position: relative;
    }
    

    .description {
        display: none;
        background-color: rgba(0, 0, 0, 0.8);
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        padding: 20px;
        position: absolute;
        top: 0px;
        left: 0px;
    }

    .poster_path:hover .description {
        display: block;
        border: 1px solid white;
        margin: 10px;
    }

    .poster_path {
        height: 100%;
        padding: 10px;
    }

    .poster_path > img{
        border: 1px solid white;
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
    }

    .vote_average {
        display: inline;
    }

    .original_language img {
        width: 15px;
    }
</style>