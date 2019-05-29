<template>
  <div class="header">
    <div class="header-left"><div class="iconfont back-icon">&#xe600;</div></div>
    <div class="header-input"><span class="iconfont">&#xe631;</span>Input Cities / Attractions / Themes</div>
    <div class="header-right">Cities
      <span class="iconfont arrow-down">&#xe776;</span>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/variables.styl';
.header
  display: flex
  line-height: .86rem
  background: $bgColor
  color: #fff
  .header-left
    width: .64rem
    float: left
    .back-icon
      text-align: center
      font-size: .4rem
  .header-right
    width: 1.24rem
    float: right
    text-align: center
    .arrow-down
      font-size: .24rem
      margin-left: -.04rem
  .header-input
    flex 1 
    background #fff
    border-radius .1rem
    margin-top .12rem
    line-height .64rem
    height .64rem
    margin-left .12rem
    color #ccc
    padding-left: .2rem
</style>