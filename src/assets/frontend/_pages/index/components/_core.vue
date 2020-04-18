<template lang="pug">
    .core-holder
        .container
            card(:xmedia = 'false')
                cardWrapper(:card = 'isResponsive', :order= 'order')
                    heading(:heading = 'core.heading')
                cardWrapper(:card = 'isResponsive')
                    videoBanner(:video = 'core.video')
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
            core : Object
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
            },

            order : function() {
                return this.is1025 ? 2 : 0
            }
        },
    }
</script>

<style lang="scss" scoped>
    @import './../../../style/config.scss';
    
    .core-holder {
        background: rgb(34,193,195);
        background: linear-gradient(180deg, rgba(34,193,195,1) 0%, rgba(68,129,173,1) 100%);
        padding-top: 25px;
        padding-bottom: 25px;
    }

    /deep/ .heading-component {
        @include media(dp-up) {
            padding-top: 25px;
            padding-bottom: 25px;
            margin-left: 25px;
        }
    }
</style>
