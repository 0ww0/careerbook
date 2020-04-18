<template lang="pug">
    .heading-component
        .title
            span {{ heading }}
</template>

<script>
    export default {
        props : {
            heading : String
        }
    }
</script>

<style lang="scss" scoped>
    @import '../../style/config.scss';

    .heading-component {
        @include fs(32)
        @include color($white)
        font-weight: 500;
        letter-spacing: .1em;
    }
</style>
