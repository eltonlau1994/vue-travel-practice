<template>
    <div class="city-header">
        City
        <router-link to="/">
            <div class="header-back"><div class="iconfont back-icon">&#xe600;</div></div>
        </router-link>

    </div>
</template>

<script>
export default {
    name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
    @import '~@/assets/styles/variables.styl';
    .city-header
        position relative
        height .86rem
        line-height .86rem
        overflow hidden
        text-align center
        color #fff
        background $bgColor
        font-size .32rem
        .header-back
            position absolute
            top 0
            left 0
            width .64rem
            text-align center
            font-size .4rem
            color #fff
</style>
