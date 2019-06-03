<template>
    <div class="city">
        <CityHeader></CityHeader>
        <CitySearch></CitySearch>
        <List></List>
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
    }
}
</script>

<style lang="stylus" scoped>

</style>
