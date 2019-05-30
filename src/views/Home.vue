<template>
  <div class="home">
    <Header :city="city"></Header>
    <HomeSwiper :list="swiperList"></HomeSwiper>
    <HomeIcons :list="iconList"></HomeIcons>
    <HomeRecommend :list="recommendList"></HomeRecommend>
    <HomeWeekend :list="weekendList"></HomeWeekend>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import HomeSwiper from '@/components/Swiper.vue'
import HomeIcons from '@/components/Icons.vue'
import HomeRecommend from '@/components/Recommend.vue'
import HomeWeekend from '@/components/HomeWeekend.vue'

export default {
  name: 'home',
  components: {
    Header,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data() {
    return {
      city: '',
      swiperList: [],
      weekendList: [],
      recommendList: [],
      iconList: []
    }
  },
  methods: {
    getHomeInfo() {
      this.axios.get('https://easy-mock.com/mock/5cef72f77b61f7101ff66f28/mock/index')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.recommendList = data.recommendList
        this.iconList = data.iconList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>
