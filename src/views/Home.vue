<template>
  <div class="home">
    <Header></Header>
    <HomeSwiper></HomeSwiper>
    <HomeIcons></HomeIcons>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import HomeSwiper from '@/components/Swiper.vue'
import HomeIcons from '@/components/Icons.vue'

export default {
  name: 'home',
  components: {
    Header,
    HomeSwiper,
    HomeIcons
  }
}
</script>
