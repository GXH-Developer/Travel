<template>
    <div class="header">
        城市选择
        <router-link to="/">
        <div class="header-right">{{city}}
            <span class="iconfont header-back">&#xe624;</span>
        </div>
        </router-link>
    </div>
</template>

<script>
export default {
  name: 'CityHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibales.styl';
  .header
    position relative
    overflow :hidden
    height :$header-height
    line-height :$header-height
    text-align :center
    color :#fff
    background :$color-bg
    font-size :.32rem
    .header-back
      position :absolute
      top :0
      left :0
      width :.64rem
      text-align :center
      font-size :.4rem
      color :#fff
</style>
