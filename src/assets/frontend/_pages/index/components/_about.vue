<template lang="pug">
    .about-holder
        .container
            .title
                span {{ about.heading }}
            .text
                p(v-for = 'data in about.text', :key = 'data.id') {{ data.paragraph }}
</template>

<script>
    export default {
        props : {
            about : Object
        }
    }
</script>

<style lang="scss" scoped>
    @import './../../../style/config.scss';

    .about-holder {
        padding-top: 45px;
        padding-bottom: 45px;
    }

    .title {
        @include fs(24)
        @include weight(500)
        margin-bottom: 25px;
    }

    .text {
        @include fs(16)
        p {
            &:not(:last-child) {
                margin-bottom: 25px;
            }
        }
    }
</style>
