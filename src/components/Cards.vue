<template>
    <div class="cards">
        <Card
            v-for="card in data"
            :card="card"
            :key="card.id"
        />
    </div>
</template>

<script>
import Card from './Card';

export default {
    name: 'Cards',
    components: {
        Card,
    },
    props: {
        data: {
            type: Array,
            require: true,
        }
    },
}
</script>
<style lang="scss" scoped>
    .cards {
        display: grid;
        gap: 20px;
        grid-template-areas: '. . . .';

        @media screen and (max-width: 1200px) {
            grid-template-areas: '. . .';
        }

        @media screen and (max-width: 768px) {
            grid-template-areas: '. .';
        }

        @media screen and (max-width: 480px) {
            grid-template-areas: '.';
        }
    }

</style>