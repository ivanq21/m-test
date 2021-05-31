<template>
    <div class="cards">
        <div
            class="card"
            :class="card.id"
            v-for="card in data"
            :key="card.id"
            :style="{ backgroundImage: 'url(' + card.bg_img + ')' }"
        >
            <div class="card__head">
                <img v-if="card.logo" :src="card.logo" alt="">
                <div v-else class="card__title">{{card.title}}</div>
                <div class="card__icon" :style="{ backgroundImage: 'url(' + card.icon + ')' }"></div>
            </div>
            <div class="card__description">
                {{card.subtitle}}
            </div>
            <div class="card__footer">
                <Button
                    :class="{
                        pink: card.id == 'mail_cloud',
                        small: card.id == 'mail_cloud',
                    }"
                    :disabled="card.id == 'ai_learn'"
                    :text="card.btn_text"
                />
            </div>
        </div>
    </div>
</template>

<script>
import Button from './Button';

export default {
    name: 'Cards',
    components: {
        Button,
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

.card {
    display: flex;
    flex-direction: column;
    width: 25%;
    max-width: 260px;
    height: 380px;
    padding: 32px;
    margin: 0 0 20px 20px;
    border: 1px solid #5540CC;
    background-repeat:  no-repeat;
    background-position: bottom right;
    background-size: 100px;
    cursor: pointer;
    transition: .3s all;

    &:hover {
        transform: translateY(-20px);
    }

    &.kubernetes {
        background-color: #4633B3;
        background-position: bottom -20px right -20px;
        background-size: 130px;

        .card__description {
            color: #fff;
        }
    }

    &:nth-child(4) {
        margin-right: 0;
        border-top-right-radius: 24px;
    }

    &__head {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 8px;
    }

    &__title {
        font-size: 20px;
        font-weight: 700;
        margin-bottom: 8px;
        max-width: 140px;
    }

    &__description {
        font-size: 17px;
        color: #B0A3FD;
        font-weight: 400;
        max-width: 210px;
        margin-bottom: auto;
    }

    &__icon {
        width: 40px;
        height: 40px;
        background-size: contain;
        background-repeat: no-repeat;
        background-position: center;
    }

    @media screen and (max-width: 1200px) {
        border-radius: 0;
        padding: 24px;
        max-width: 260px;
        min-width: calc(33% - 20px);

        &:nth-child(7) {
            border-top-right-radius: 0;
            border-bottom-left-radius: 24px;
        }

        &:nth-child(3) {
            border-top-right-radius: 24px;
        }

        &:nth-child(4) {
            border-radius: 0;
        }
    }

    @media screen and (max-width: 768px) {
        border-radius: 0;
        min-width: calc(50% - 20px);
        max-width: unset;

        &:nth-child(3) {
            border-top-right-radius: 0;
            border-bottom-left-radius: 24px;
        }

        &:nth-child(2) {
            border-top-right-radius: 24px;
        }
    }

    @media screen and (max-width: 480px) {
        width: 100%;
    }
}

</style>