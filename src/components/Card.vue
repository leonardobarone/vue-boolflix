<template>
    <div class="card">
        <div class="title">
            {{card.title}}
        </div>
        <div class="original_title">
            {{card.original_title}}
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
        border: 1px solid black;
        .original_language img {
            width: 15px;
        }
    }
</style>