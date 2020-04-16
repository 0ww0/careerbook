<template lang="pug">
    .wrapper-header
        .hero.container
            span.bold C
            span.light areer
            span.bold B
            span.light ook
</template>

<script>
    export default {
    }
</script>

<style lang="scss" scoped>
    @import './../../style/config.scss';

    .wrapper-header {
        position: relative;
        display: block;
        width: 100%;
        z-index: 1;
        @include background(#4481ad)
    }

    .hero {
        @include fs(18)
        padding-top: 15px;
        padding-bottom: 15px;
        @include color($white)
        letter-spacing: .15em;
        .bold {
            @include weight(500)
        }

        .light {
            @include weight(300)
        }
    }
</style>
