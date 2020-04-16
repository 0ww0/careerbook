<template lang="pug">
    .wrapper-content
        banner(:heading = 'heading', :video = 'video')
</template>

<script>
    import banner from './components/_banner.vue'

    export default {
        components : {
            banner,
        },

        data() {
            return {
                heading : "Discover your next career move with Photobook Worldwide!",
                video : '../assets/video/1.mp4'
            }
        }
    }
</script>
