<template>
    <div class="detail">
        <DetailBanner 
            :sightName='sightName'
            :bannerImg='bannerImg'
            :galleryImgs='galleryImgs'
        ></DetailBanner>
        <DetailHeader></DetailHeader>
        <div class="content">
            <DetailList :list="list"></DetailList>
        </div>
    </div>
</template>

<script>
import DetailBanner from '@/components/DetailBanner'
import DetailHeader from '@/components/DetailHeader'
import DetailList from '@/components/DetailList'

export default {
    components: {
        DetailBanner,
        DetailHeader,
        DetailList
    },
    data () {
        return {
            sightName: '',
            bannerImg: '',
            galleryImgs: [],
            list: []
        }
    },
    methods: {
        getDetailInfo () {
           this.axios.get('https://easy-mock.com/mock/5cef72f77b61f7101ff66f28/mock/detail', {
                params: {
                    id: this.$route.params.id
                }
            }).then(this.handleGetDataSucc)

        },
        handleGetDataSucc (res) {
            res = res.data
            if (res.ret && res.data) {
                const data = res.data
                this.sightName = data.sightName
                this.bannerImg = data.bannerImg
                this.galleryImgs = data.galleryImgs
                this.list = data.categoryList
            }
        }
    },
    mounted () {
        this.getDetailInfo()
    }
}
</script>

<style lang="stylus" scoped>
    .content
        height 50rem
</style>
