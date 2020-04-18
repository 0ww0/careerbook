<template lang="pug">
    .job-holder
        .container
            .title
                span Join Photobook Worldwide team
            .filter-holder
                .dropdown
                    select(name = 'sort', v-model = 'type_filter')
                        option(disabled, value = '') Work Type
                        option(v-for = 'data in type', :value='data.title') {{ data.title }}
                .dropdown
                    select(name = 'sort', v-model = 'location_filter')
                        option(disabled, value = '') Location
                        option(v-for = 'data in location', :value='data.title') {{ data.title }}
                .dropdown
                    select(name = 'sort', v-model = 'category_filter')
                        option(disabled, value = '') Category
                        option(v-for = 'data in category', :value='data.title') {{ data.title }}
            .content-holder
                card(stretch, :xmedia = 'false')
                    cardWrapper(:card = 'isResponsive', v-for = 'data in listArray', :key = 'data.id')
                        joblist(:job = 'data', @open = "showModal('listing', data)")
                    .no-listing(v-if = 'listArray.length === 0')
                        p No available job posting
            modal(ref='listing', overlayTheme = 'dark', blocking, @close = 'clearListing')
                joblisting(:listing = 'listing')
</template>

<script>
    import Media from './../../../_shares/media.js'
    import card from './../../../_components/card/_card.vue'
    import cardWrapper from './../../../_components/card/_wrapper.vue'
    import joblist from './../../../_components/post/_list.vue'
    import modal from './../../../_components/modal/_modal.vue'
    import joblisting from './../../../_components/post/_listing.vue'

    export default {
        extends : Media,

        components : {
            card,
            cardWrapper,
            joblist,
            modal,
            joblisting
        },

        data() {
            return {
                type_filter : '',
                location_filter : '',
                category_filter : '',
                listing: {},
                type: [
                    {
                        id: 1,
                        title : 'Full-Time'
                    },
                    {
                        id: 2,
                        title : 'Intern'
                    }
                ],
                location : [
                    {
                        id: 1,
                        title : 'All'
                    },
                    {
                        id: 2,
                        title : 'Bangsar South, Malaysia'
                    },

                    {
                        id: 3,
                        title : 'Indonesia'
                    },

                    {
                        id: 4,
                        title : 'The Columbia Tower, Mandaluyong City, Philippines'
                    }
                ],
                category : [
                    {
                        id: 1,
                        title : 'All'
                    },
                    {
                        id: 2,
                        title : 'Marcomms + Creative (Campaign & Enterprise) – Affiliate Marketing'
                    },

                    {
                        id: 3,
                        title : 'Marcomms + Creative (Campaign & Enterprise) – Brand & Campaign Management'
                    },

                    {
                        id: 4,
                        title : 'Marcomms + Creative (Campaign & Enterprise) – Performance Marketing & App Marketing'
                    },

                    {
                        id: 5,
                        title : 'Marketing (Indonesia) – Digital Marketing Analyst'
                    },
                    {
                        id: 6,
                        title : 'Software Engineering (Philippines) – Software Engineering (Philippines)'
                    },

                    {
                        id: 7,
                        title : 'Customer Experience'
                    },

                    {
                        id: 8,
                        title : 'ITSE'
                    },

                    {
                        id: 9,
                        title : 'Product Tech'
                    },

                    {
                        id: 10,
                        title : 'Sales'
                    }
                ],
                list : [
                    {
                        id: 1,
                        title: 'Affiliate Marketing Manager',
                        location: 'Bangsar South, Malaysia',
                        category: 'Marcomms + Creative (Campaign & Enterprise) – Affiliate Marketing',
                        type: 'Full-Time',
                        modal: {

                        }
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

            listArray() {
                let filterType = this.type_filter,
                    filterLocation = this.location_filter,
                    filterCategory = this.category_filter
                return this.list.filter(function(item){
                    let filtered = true
                    if(filterType && filterType.length > 0) {
                        filtered = item.type == filterType
                    }
                    if(filtered){
                        if(filterLocation && filterLocation.length > 0) {
                            if(filterLocation == '' || filterLocation == 'All') {
                                return filtered = item
                            }
                            filtered = item.location == filterLocation
                        }
                    }
                    if(filtered){
                        if(filterCategory && filterCategory.length > 0) {
                            if(filterCategory == '' || filterCategory == 'All') {
                                return filtered = item
                            }
                            filtered = item.category == filterCategory
                        }
                    }
                    return filtered
                })
            },
        },

        methods : {
            showModal(ref, data) {
                if (this.$refs[ref]) {
                    this.$refs[ref].open()
                    this.listing = data
                } else {
                    throw new Error('Ref not defined: ' + ref)
                }
            },

            clearListing() {
                this.listing = {}
            }
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

    .dropdown {
        width: 200px;
        &:not(:last-child){
            margin-right: 10px;
        }
        select {
            width: 100%;
            padding: 5px 15px;
        }
    }

    .no-listing {
        display: block;
        @include fs(20)
        @include weight(500)
        margin-top: 105px;
        margin-bottom: 105px;
    }

    /deep/ .modal {
        max-width: 600px;
    }
</style>
