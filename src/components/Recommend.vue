<template>
    <div class="home-recommend">
        <div class="title">Recommendation</div>
        <ul>
            <router-link tag="li" class="item border-bottom" v-for="item of recommendList" :key='item.id' :to="'/detail/' + item.id">
                <img :src="item.imgUrl" class="item-img">
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-desc"> {{ item.desc }}</p>
                    <button class="item-button">Click</button>
                </div>
            </router-link>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HomeRecommend',
    data() {
        return {
            recommendList: [{
                id: 1,
                imgUrl: 'https://imgs.qunarzz.com/sight/p0/1902/84/84696f368bbec10da3.img.jpg_200x200_50323152.jpg',
                title: 'World Expo',
                desc: 'The best world expo in the world'
        },
        {
                id: 2,
                imgUrl: 'https://imgs.qunarzz.com/sight/p0/1902/84/84696f368bbec10da3.img.jpg_200x200_50323152.jpg',
                title: 'World Expo',
                desc: 'The best world expo in the world'
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
    .item
        overflow hidden
        display flex
        height 1.9rem
        .item-img
            width 1.7rem
            height 1.7rem
            padding .1rem
        .item-info
            flex 1
            padding .1rem
            min-width 0
            .item-title
                line-height .54rem
                font-size: .32rem
                ellipsis()
            .item-desc
                line-height .4rem
                color #ccc
                ellipsis()
            .item-button
                line-height .44rem
                margin-top: .16rem
                background #ff9300
                padding 0 .2rem
                border-radius: .06rem
                color #fff
</style>
