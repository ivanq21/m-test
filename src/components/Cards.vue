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
        display: flex;
        flex-wrap: wrap;
        margin-left: -20px;
    }
</style>