<template lang="pug">
    .wrapper-content
        banner(:banner = 'banner')
        about(:about = 'about')
        core(:core = 'core')
        job
</template>

<script>
    import banner from './components/_banner.vue'
    import about from './components/_about.vue'
    import core from './components/_core.vue'
    import job from './components/_job.vue'

    export default {
        components : {
            banner,
            about,
            core,
            job
        },

        data() {
            return {
                banner : {
                    heading : "Discover your next career move with Photobook Worldwide!",
                    video : '../assets/video/2.mp4',
                },
                core : {
                    heading : "At Photobook Worldwide, we uphold our core value principle.",
                    video : '../assets/video/1.mp4',
                },
                about: {
                    heading : "Get to know what Photobook Worldwide is all about",
                    text : [
                        {
                            id: 1,
                            paragraph : "At Photobook Worldwide, we want to celebrate life with all your greatest memories through personalisation. We make personalisation easily accessible to everyone by providing the perfect online platform along with a wide selection of Photo Books and Photo Albums. With various photo book sizes, papers, covers and accessories available, our free readybooks are designed to inspire your creativity along with our easy-to-use online photo book maker. Whether it's to remember your travel holiday, wedding ceremony, Christmas or New Year, printing a custom photo book with us ensures your picture-perfect moments are preserved for many years down the road.",
                        },
                        {
                            id: 2,
                            paragraph : "Besides photo books, Photobook Worldwide also offer the best personalisable prints such as canvas prints, cards, stationeries, calendars, prints and photo gifts. We believe your memories should be printed on more than just albums that you can share and admire wherever you are - like a tumbler for the on-the-go and a desk calendar for your office table. Don't forget to keep your home looking good with custom wall decor like metal prints and photo tiles, adding a contemporary style at the same time.",
                        },
                        {
                            id: 3,
                            paragraph : "Make your own gifts for any occasion including wedding, travel, baby milestone, birthday, graduation, special celebration such as Christmas and Valentine's Day. Curate your best photographs and create a custom gift today through the simple online designer that is programmed with useful tools for every personalisation need.",
                        },
                        {
                            id: 4,
                            paragraph : "No more worries about finding the perfect gifts because nothing is more unique than personalised gifts from the heart.",
                        }
                    ]
                }
            }
        }
    }
</script>
