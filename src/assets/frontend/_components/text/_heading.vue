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
        padding-top: 25px;
        padding-bottom: 25px;
        @include fs(26)
        @include color($white)
        font-weight: 500;
        letter-spacing: .1em;
    }
</style>
