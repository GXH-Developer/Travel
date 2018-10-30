<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="输入城市名或者拼音"/>
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibales.styl';
  .search
    height :.72rem
    padding : .1rem
    background :$color-bg
    box-sizing :border-box
    .search-input
      float left
      width :100%
      height :.52rem
      box-sizing :border-box
      line-height :.52rem
      text-align :center
      border :none
      border-radius :.06rem
      color :#666
      box-sizing :border-box
      outline: none
</style>
