<template>
    <div class="card col-12 col-md-2">
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
        <div class="vote_average">
            {{card.vote_average}}
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
    .card {
        background-color: var(--nero);
        border: 1px solid white;
        .original_language img {
            width: 15px;
        }
    }
</style>