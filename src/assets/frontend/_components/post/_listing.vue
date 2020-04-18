<template lang="pug">
    .listing-component
        span {{ listing.title }}
</template>

<script>
    export default {
        props : {
            listing : Object
        }
    }
</script>

<style lang="scss" scoped>
    .listing-component {
        width: 100%;
        height: 540px;
    }
</style>
