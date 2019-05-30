<template>
    <div class="home-weekend">
        <div class="title">Home Weekend</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key='item.id'>
                    <div class="item-img-wrapper"><img :src="item.imgUrl" class="item-img"></div>
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-desc"> {{ item.desc }}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HomeWeekend',
    data() {
        return {
            recommendList: [{
                id: 1,
                imgUrl: 'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
                title: 'Beautiful Garden',
                desc: 'Search for the most beautiful garden in China'
        },
        {
                id: 2,
                imgUrl: 'https://imgs.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
                title: 'Weekend City',
                desc: 'Spend time in the Palace in your weekend!'
        }]
        }

    }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/mixins.styl';
    .title
        margin-top .2rem
        line-height .8rem
        background #eee
        text-indent: .2rem
    .item-img-wrapper
        overflow hidden
        height: 0
        padding-bottom 33.9%
        .item-img
            width 100%
    .item-info
        padding: .1rem
        .item-title
            line-height .54rem
            font-size: .32rem
            ellipsis()
        .item-desc
            line-height .4rem
            color #ccc
            ellipsis()

</style>
