<template lang="pug">
    .list-component(@click = 'open')
        .title
            span {{ job.title }}
        .location
            span {{ job.location }}
        .posting
            .category
                span {{ job.category }}
            .type
                span {{ job.type }}
</template>

<script>
    export default {
        props : {
            job : Object
        },

        methods : {
            open() {
                this.$emit('open')
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import './../../style/config.scss';

    .list-component {
        border: 1px solid;
        border-radius: 10px;
        @include border(#ddd)
        height: 100%;
        box-shadow: none;
        cursor: pointer;
        &:hover {
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
            @include trans-prop(box-shadow)
        }

        display: flex;
        flex-direction: column;
        flex-flow: column nowrap;
        justify-content: flex-start;
    }

    .title {
        @include fs(24)
        @include weight(500)
        padding: 10px 20px 0;
    }

    .location {
        @include fs(14)
        @include weight(400)
        padding: 0 20px 5px;
    }

    .posting {
        margin-top: auto;
    }

    .category {
        @include fs(14)
        @include weight(400)
        padding: 5px 20px;
    }

    .type {
        border-top: 1px solid;
        padding: 5px 20px;
        @include fs(14)
        @include weight(300)
        @include color($darkGrey)
        @include border(#ddd)
    }
</style>
