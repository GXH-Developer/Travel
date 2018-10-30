<template>
    <div class="header">
        <div class="header-left">
          <span class="iconfont back-icon">&#xe624;</span>
        </div>
        <div class="header-input">输入城市/景点/游玩主题</div>
        <router-link to="/city">
          <div class="header-right">{{this.city}}
            <span class="arrow-icon"></span>
          </div>
        </router-link>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    'city': String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibales.styl';
  .header
    display: flex
    height: $header-height
    font-size .3rem
    line-height: $header-height
    background-color : $color-bg
    .header-left
      width: .64rem
      float: left
      text-align :center
      color: #fff
      .back-icon
        font-size :.4rem
        text-align :center
    .header-input
      flex: 1
      height: .64rem
      line-height: .64rem
      margin-left: .2rem
      margin-top: .12rem
      background: #fff
      border-radius: .1rem
      color :#fff
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      color : #fff
</style>
