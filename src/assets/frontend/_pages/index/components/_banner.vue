<template lang="pug">
    .banner-holder
        .container
            card(:xmedia = 'false')
                cardWrapper(:card = 'isResponsive')
                    heading(:heading = 'banner.heading')
                cardWrapper(:card = 'isResponsive')
                    videoBanner(:video = 'banner.video')
</template>

<script>
    import Media from './../../../_shares/media.js'
    import card from './../../../_components/card/_card.vue'
    import cardWrapper from './../../../_components/card/_wrapper.vue'
    import heading from './../../../_components/text/_heading.vue'
    import videoBanner from './../../../_components/banner/_video.vue'

    export default {
        extends : Media,

        props : {
            banner : Object
        },

        components : {
            card,
            cardWrapper,
            heading,
            videoBanner
        },

        computed : {
            isResponsive () {
                if(this.is1025) {
                    return 'half'
                } else {
                    return 'full'
                }
            }
        },
    }
</script>

<style lang="scss" scoped>
    .banner-holder {
        background: rgb(34,193,195);
        background: linear-gradient(0deg, rgba(34,193,195,1) 0%, rgba(68,129,173,1) 100%);
        padding-top: 25px;
        padding-bottom: 25px;
    }

    /deep/ .heading-component {
        @include media(dp-up) {
            padding-top: 25px;
            padding-bottom: 25px;
            margin-right: 25px;
        }
    }
</style>
