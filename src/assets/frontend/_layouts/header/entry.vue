<template lang="pug">
    .wrapper-header
        .hero.container
            span.bold C
            span areer
            span.bold B
            span ook
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
        @include fs(16)
        padding-top: 25px;
        padding-bottom: 25px;
        @include color($white)
        letter-spacing: .15em;
        .bold {
            font-weight: 500;
        }
    }
</style>
