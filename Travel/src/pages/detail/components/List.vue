<template>
  <div>
    <div class="item"
      v-for="(item,index) of list" :key="index"
    >
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div class="item-children" v-if="item.children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .item-title-icon
    position :relative
    left :.05rem
    top :.06rem
    display :inline-block
    width :.36rem
    height :.36rem
    background :url('http://www.52programer.com/template/comiis_mi/img/dlogo.jpg') 0 0 no-repeat;
    margin-right :.1rem
    background-size: .35rem .3rem
  .item-title
    line-height :.8rem
    font-size :.32rem
  .item-children
    padding :0 .2rem
</style>
