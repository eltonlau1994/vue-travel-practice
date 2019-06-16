<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1801/4e/4ee5653be58dcb1a3.water.jpg_600x330_f82a1d80.jpg">
            <div class="banner-info">
                <div class="banner-title">Hong Kong Disneyland</div>
                <div class="banner-number">
                    <span class="iconfont banner-icon">&#xe610;</span>
                    15
                </div>
            </div>
        </div>
        <Fade>
            <CommonGallery 
            :images="imgs" 
            v-show="showGallery"
            @close="handleBannerClose"></CommonGallery>
        </Fade>
    </div>
</template>

<script>
import CommonGallery from '@/common/gallery/Gallery'
import Fade from '@/common/fade/Fade'

export default {
    data() {
        return {
            showGallery: false,
            imgs: [
                'http://img1.qunarzz.com/sight/p0/1801/4e/4ee5653be58dcb1a3.water.jpg_r_800x800_279b846f.jpg',
                'http://img1.qunarzz.com/sight/p0/1803/56/56f59615373d8dbba3.water.jpg_r_800x800_31653ab3.jpg'
            ]
        }
    },
    methods: {
        handleBannerClick() {
            this.showGallery = true
        },
        handleBannerClose () {
            this.showGallery = false
        }
    },
    components: {
        CommonGallery,
        Fade
    }
}


</script>

<style lang="stylus" scoped>
    .banner
        position relative
        overflow hidden
        height 0
        padding-bottom 55%
        .banner-img
            width 100%
        .banner-info
            display flex
            position absolute
            left 0
            right 0
            bottom 0
            line-height .6rem
            color #fff
            background-image linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
            .banner-title
                font-size .32rem
                flex 1
                padding 0 .2rem
            .banner-number
                margin-top .14rem
                padding 0 .4rem 
                line-height .32rem
                height .32rem
                border-radius .2rem
                background rgba(0, 0, 0, .8)
                font-size .24rem
                .banner-icon
                    font-size .24rem
</style>
