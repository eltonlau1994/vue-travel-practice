<template>
    <div>
        <div class="search">
            <input v-model="keyword" class="search-input" type="text" placeholder="Input City Name">
        </div>
        <div class="search-content" ref="search" v-show="keyword">
            <ul>
                <li class="search-item border-bottom" v-for="item of list" :key="item.id" @click="handleCityClick(item.name)"> {{item.name}}</li>
                <li class="search-item border-bottom" v-show="hasNoData">Cannot find matched result</li>
            </ul>
        </div>
    </div>
</template>

<script>
import { clearTimeout, setTimeout } from 'timers';
import Bscroll from 'better-scroll'
export default {
    name: 'CitySearch',
    props: {
        cities: Object
    },
    data() {
        return {
            keyword: '',
            list: [],
            timer: null
        }
    },
    methods: {
        handleCityClick(city){
            this.$store.dispatch('changeCity', city)
            this.$router.push('/')
        }
    },
    watch: {
        keyword() {
            if(this.timer) {
                clearTimeout(this.timer)
            }
            if (!this.keyword) {
                this.list = []
                return
            }
            this.timer = setTimeout(() => {
                const result = []
                for(let i in this.cities){
                    this.cities[i].forEach((value) => {
                        if(value.name.indexOf(this.keyword) > -1) {
                            result.push(value)
                        }
                    })
                }
                this.list = result
            }, 100)
        }
    },
    mounted () {
        this.scroll = new Bscroll(this.$refs.search)
    },
    computed: {
        hasNoData() {
            return !this.list.length
        }
    }
}
</script>

<style lang="stylus" scoped>
    @import '~@/assets/styles/variables.styl';
    .search
        padding: 0 .1rem
        height .72rem
        background $bgColor
        .search-input
            box-sizing  border-box
            height .62rem
            line-height .62rem
            width 100%
            text-align center
            border-radius .06rem
            color #666
            padding 0 .1rem
    .search-content
        z-index 1
        overflow hidden
        position absolute
        top 1.58rem
        left 0
        right 0
        bottom 0
        background #eee
        .search-item
            line-height .62rem
            padding-left .2rem
            color #666
            background #fff

</style>
