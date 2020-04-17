<template lang="pug">
    .job-holder
        .container
            .title
                span Join Photobook Worldwide team
            .filter-holder
                .dropdown
                    select(name = 'sort', v-model = 'type_filter')
                        option(disabled, value = '') Work Type
                        option( value = 'All') All
                        option(value='Full-Time') Full-Time
                        option(value='Intern') Intern
                .dropdown
                    select(name = 'sort', v-model = 'location_filter')
                        option(disabled, value = '') Location
                        option(value = 'All') All
                        option(value='Bangsar South, Malaysia') Bangsar South, Malaysia
                        option(value='Indonesia') Indonesia
                        option(value='The Columbia Tower, Mandaluyong City, Philippines') The Columbia Tower, Mandaluyong City, Philippines
            .content-holder
                card(stretch, :xmedia = 'false')
                    cardWrapper(:card = 'isResponsive', v-for = 'data in selectArray()', :key = 'data.id')
                        joblist(:job = 'data')
</template>

<script>
    import Media from './../../../_shares/media.js'
    import card from './../../../_components/card/_card.vue'
    import cardWrapper from './../../../_components/card/_wrapper.vue'
    import joblist from './../../../_components/post/_list.vue'

    export default {
        extends : Media,

        components : {
            card,
            cardWrapper,
            joblist
        },

        data() {
            return {
                filter: '',
                type_filter : '',
                location_filter : '',
                list : [
                    {
                        id: 1,
                        title: 'Affiliate Marketing Manager',
                        location: 'Bangsar South, Malaysia',
                        category: 'Marcomms + Creative (Campaign & Enterprise) – Affiliate Marketing',
                        type: 'Full-Time'
                    },

                    {
                        id: 2,
                        title: 'Assistant Manager, Social Media',
                        location: 'Bangsar South, Malaysia',
                        category: 'Marcomms + Creative (Campaign & Enterprise) – Brand & Campaign Management',
                        type: 'Full-Time'
                    },

                    {
                        id: 3,
                        title: 'Marketing Intern (App)',
                        location: 'Bangsar South, Malaysia',
                        category: 'Marcomms + Creative (Campaign & Enterprise) – Performance Marketing & App Marketing',
                        type: 'Intern'
                    },

                    {
                        id: 4,
                        title: 'Digital Marketing Analyst',
                        location: 'Indonesia',
                        category: 'Marketing (Indonesia) – Digital Marketing Analyst',
                        type: 'Full-Time'
                    },

                    {
                        id: 5,
                        title: 'Associate Software Engineer (Full Stack)',
                        location: 'The Columbia Tower, Mandaluyong City, Philippines',
                        category: 'Software Engineering (Philippines) – Software Engineering (Philippines)',
                        type: 'Full-Time'
                    },

                    {
                        id: 6,
                        title: 'Customer Experience Specialist',
                        location: 'Indonesia',
                        category: 'Customer Experience',
                        type: 'Full-Time'
                    },

                    {
                        id: 7,
                        title: 'Database Engineer',
                        location: 'Bangsar South, Malaysia',
                        category: 'ITSE',
                        type: 'Full-Time'
                    },

                    {
                        id: 8,
                        title: 'Front-End Developer',
                        location: 'Bangsar South, Malaysia',
                        category: 'Product Tech',
                        type: 'Full-Time'
                    },

                    {
                        id: 9,
                        title: 'Head of Sales',
                        location: 'Bangsar South, Malaysia',
                        category: 'Sales',
                        type: 'Full-Time'
                    },
                ]
            }
        },

        computed : {
            isResponsive () {
                if(this.is1025) {
                    return 'one-quarter'
                } else if(this.is801) {
                    return 'one-third'
                } else if(this.is641) {
                    return 'half'
                } else {
                    return 'full'
                }
            },

            typeArray() {
                if(this.type_filter == '' || this.type_filter == 'All') return this.list
                return this.list.filter(function(item) {
                    return item.type === this.type_filter
                }.bind(this))
            },

            locationArray() {
                if(this.location_filter == '' || this.location_filter == 'All') return this.list
                return this.list.filter(function(item) {
                    return item.location === this.location_filter
                }.bind(this))
            },
        },

        methods : {
            selectArray() {
                if(this.type_filter) { return this.typeArray }
                else if(this.location_filter) { return this.locationArray }
                else {return this.list}
            }
        },
        mounted() {
            console.log(this.selectArray())
        }
    }
</script>

<style lang="scss" scoped>
    @import './../../../style/config.scss';

    .job-holder {
        padding-top: 25px;
        padding-bottom: 25px;
    }

    .title {
        @include fs(24)
        @include weight(500)
        margin-bottom: 25px;
    }

    .filter-holder {
        display: flex;
        flex-direction: row;
        flex-flow: row nowrap;
        align-items: flex-end;
        justify-content: flex-end;
    }
</style>
