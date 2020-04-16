<template lang="pug">
    .wrapper-footer
        .copyright
            span &copy; 2020 CareerBook. All Rights Reserved.
</template>

<script>
    export default {
    }
</script>

<style lang="scss" scoped>
    @import './../../style/config.scss';

    .wrapper-footer {
        padding-top: 15px;
        padding-bottom: 15px;
    }

    .copyright {
        text-align: center;
        @include fs(10)
    }
</style>
