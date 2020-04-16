<template lang="pug">
    .banner-component.video
        video(controls)
            source(:src='video')
</template>

<script>
    export default {
        props : {
            video: String,
        }
    }
</script>

<style lang="scss" scoped>
    @import '../../style/config.scss';

    .video{
        position: relative;
        overflow: hidden;
        padding-bottom: 56.5%;
        max-width: 100%;
        border-radius: 10px;
        box-shadow: 0 8px 10px rgba(0, 0, 0, .5);
        video{
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
    }
</style>
