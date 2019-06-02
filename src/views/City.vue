<template>
    <div class="city">
        <CityHeader></CityHeader>
        <CitySearch></CitySearch>
    </div>
</template>

<script>
import CityHeader from '@/components/CityHeader.vue'
import CitySearch from '@/components/CitySearch.vue'

export default {
    name: 'City',
    components: {
        CityHeader,
        CitySearch
    }
}
</script>

<style lang="stylus" scoped>

</style>
