<template>
    <div class="city">
        <CityHeader></CityHeader>
        <CitySearch :cities="cities"></CitySearch>
        <List :cities="cities" :hot="hotCities"></List>
    </div>
</template>

<script>
import CityHeader from '@/components/CityHeader.vue'
import CitySearch from '@/components/CitySearch.vue'
import List from '@/components/List.vue'


export default {
    name: 'City',
    components: {
        CityHeader,
        CitySearch,
        List
    },
    data() {
        return {
            cities: {},
            hotCities: []
        }
    },
    methods: {
        getCityInfo() {
            this.axios.get('https://easy-mock.com/mock/5cef72f77b61f7101ff66f28/mock/cities')
                .then(this.getCityInfoSucc)
        },
        getCityInfoSucc (res) {
            res = res.data
            if (res.ret && res.data) {
                const data = res.data
                this.cities = data.cities
                this.hotCities = data.hotCities
            }
        }
    },
    mounted () {
        this.getCityInfo()
    }
}
</script>

<style lang="stylus" scoped>

</style>
