<template>
    <div class="icons">
       <swiper> 
           <swiper-slide v-for="(page, index) of pages" :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class="icon-img">
                        <img class="icon-img-content" :src="item.imgUrl" />
                        <p class="icon-desc">{{item.desc}}</p>
                    </div>
                </div>
           </swiper-slide>
       </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeIcons',
    data() {
        return {
            iconList: [{
                id: 1,
                desc: "Tickets",
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'
            },
            {
                id: 2,
                desc: "Day Trip",
                imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/f0f00d6dfe038c044dbc9a437f58b0eb.png'
            },
            {
                id: 3,
                desc: "Must Have",
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
            },
            {
                id: 4,
                desc: "Anywhere",
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png'
            },
            {
                id: 5,
                desc: "Great Wall",
                imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/0334cf5430b9b5505fd79e2b8d7e8670.png'
            },
            {
                id: 6,
                desc: "Palace",
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png'
            },
            {
                id: 7,
                desc: "Zoo",
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png'
            },
            {
                id: 8,
                desc: "Auction",
                imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20195/35d83bb968d80d54926f30cfb92cb6ff.png'
            },
            {
                id: 9,
                desc: "Happy Valley",
                imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/338c5b924c5809e8c7b14f60a953c3e2.png'
            }]
        }
    },
    computed: {
        pages () {
            const pages = []
            this.iconList.forEach((item, index) => {
                const page = Math.floor(index / 8)
                if (!pages[page]) {
                    pages[page] = []
                }
                pages[page].push(item)
            })
            return pages
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/variables.styl';
@import '~@/assets/styles/mixins.styl';
    .icons >>> .swiper-container
        height: 0
        padding-bottom: 50%
        padding-top: .3rem
        .icon
            height: 0
            position: relative
            width: 25%
            float: left
            padding-bottom: 25%
            .icon-img
                position: absolute
                top: 0
                left: 0
                right: 0
                bottom: .44rem
                box-sizing: border-box
                padding: .1rem
                .icon-img-content
                    display: block
                    margin: 0 auto
                    height: 100%
            .icon-desc
                display: absolute
                left: 0
                right: 0
                bottom: 0
                height: .44rem
                line-height: .44rem
                text-align: center
                color: $darTextColor
                ellipsis()
</style>