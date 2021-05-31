<template>
    <button
        class="button"
        :class="{
            bottomRadius: borderRadius === 'bottom',
            topRadius: borderRadius === 'top',
            bothRadius: borderRadius === 'both',
        }"
    >
        {{text}}
    </button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: {
            type: String,
            require: true,
        },
        borderRadius: {
            type: String,
            default: 'both',
        }
    }
}
</script>

<style lang="scss" scoped>
    .button {
        background: none;
        border: none;
        margin: 0;
        padding: 0;
        width: auto;
        height: 40px;
        line-height: 38px;
        color: #fff;
        font-size: 17px;
        cursor: pointer;
        transition: .3s all;

        &:disabled {
            color: #998AEF;
            cursor: default;
        }

        &.pink {
            background: #FF2A7A;
            font-weight: 500;
            border: 1px solid #FF2A7A;

            &:hover {
                background: none;
                color: #FF2A7A;
            }
        }

        &.light {
            background: #4633B3;

            &:hover {
                background: #5b44df;
            }
        }

        &.small {
            width: 150px;
            padding: 0 16px;
        }

        &.big {
            width: 255px;
            height: 48px;

            @media screen and (max-width: 480px) {
                width: 100%;
            }
        }

        &.bothRadius {
            border-bottom-left-radius: 12px;
            border-top-right-radius: 12px;
        }

        &.topRadius {
            border-top-right-radius: 12px;
        }

        &.bottomRadius {
            border-bottom-left-radius: 12px;
        }
    }

</style>