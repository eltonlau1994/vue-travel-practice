<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbottom">Current City</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button"> Hong Kong</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">Popular Cities</div>
                <div class="button-list">
                    <div class="button-wrapper" v-for="item of hot" :key="item.id">
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>        
            <div class="area" v-for="(item, key) of cities" :key="item.key">
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div class="item border-topbottom" v-for="innerItem of item" :key="innerItem.id">
                        {{innerItem.name}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
    props: {
        hot: Array,
        cities: Object
    },
    mounted() {
        this.scroll = new Bscroll(this.$refs.wrapper)
    }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/mixins.styl';
    .borden-topbottom
        &:before
            border-color #ccc
        &:after
            border-color #ccc
    .list
        overflow hidden
        position: absolute
        top 1.58rem
        left 0
        right 0
        bottom 0
        .title
            line-height .54rem
            background #eee
            padding-left .2rem
            color #666
            font-size .26rem
        .button-list
            overflow hidden
            padding: .1rem
            .button-wrapper
                width 33.33%
                float left
                .button
                    text-align center
                    margin .1rem
                    border .02rem solid #ccc
                    padding .1rem 0
        .item-list
            .item
                line-height .76rem
                color #666
                padding-left .2rem
</style>
