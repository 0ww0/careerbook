<template lang="pug">
    .listing-component
        .job-description
            .title
                p {{ listing.title }}
            .location
                p {{ listing.location }}
            .category
                p {{ listing.category }}
            .type
                p {{ listing.type }}
        .job-button
            button.info Apply For This Job
</template>

<script>
    export default {
        props : {
            listing : Object
        }
    }
</script>

<style lang="scss" scoped>
    @import './../../style/config.scss';

    .listing-component {
        width: 100%;
        @include background(#ddd)

        display: flex;
        flex-direction: column;
        flex-flow: column nowrap;
        align-items: flex-start;
        justify-content: flex-start;
    }

    .job-description {
        padding: 25px;
        width: 100%;
        @include background($white)
        .title {
            @include fs(24)
            @include weight(500)
        }

        .location, .category, .type {
            @include fs(14)
            @include weight(300)
        }
    }

    .job-button {
        padding: 25px;
        width: auto;
        text-align: center;
        margin: 0 auto;

        button {
            position: relative;
            width: 100%;
            border: em(1) solid;
            text-align: center;
            padding: em(8) em(50);

            display: flex;
            flex-direction: row;
            flex-flow: row nowrap;
            justify-content: center;
            align-items: center;

            text-transform: uppercase;
            user-select: none;
            white-space: nowrap;
            cursor: pointer;
            margin: em(5) auto;

            @include media(sm-up){
                margin: em(5);
            }

            @include background($white)
            @include color($black)
            @include border($darkGrey)

            &.info {
                @include background($info)
                @include color($white)
                @include border($white, .3)
                &.outline {
                    @include background($white);
                    @include color($info)
                }
            }
            &:hover {
                @include background($black)
                @include color($white)
                @include trans-prop(background-color, color)
            }
        }
    }
</style>
