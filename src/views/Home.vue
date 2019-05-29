<template>
  <div class="home">
    <Header></Header>
    <HomeSwiper></HomeSwiper>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import HomeSwiper from '@/components/Swiper.vue'

export default {
  name: 'home',
  components: {
    Header,
    HomeSwiper
  }
}
</script>
