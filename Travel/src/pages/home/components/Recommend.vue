<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <router-link
              tag="li"
              :to="'/detail/' + item.id"
              class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <img class="item-img" :src="item.imgUrl" alt="">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <div class="item-button">查看详情</div>
                </div>
            </router-link>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl';
  .recommend-title
    font-size :.3rem
    line-height :.8rem
    background :#eee
    text-indent :.2re
   .item
     overflow :hidden
     display: flex
     height: 1.9rem
     .item-img
       width :1.7rem
       height :1.7rem
       padding :.1rem
     .item-info
       flex :1
       padding :.1rem
       min-width:0
     .item-title
       height :.54rem
       line-height :.54rem
       font-size :.32rem
       ellipsis()
      .item-desc
        line-height :.4rem
        height :.4rem
        font-size :.3rem
        color :#ccc
        ellipsis()
      .item-button
        line-height :.44rem
        height :.44rem
        font-size :.25rem
        width :1.1rem
        text-align :center
        margin-top :.16rem
        background :#ff9300
        padding :0 .1rem
        border-radius :.06rem
        color #fff
</style>
