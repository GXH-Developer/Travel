<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <img class="item-img" :src="item.imgUrl" alt="">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <div class="item-button">查看详情</div>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        'id': '0',
        'imgUrl': 'https://ss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=2593844834,2702597776&fm=58&bpow=800&bpoh=575',
        'title': '大连圣亚海洋世界',
        'desc': '浪漫大连首站，浪漫的海洋主题乐园'
      },
      {
        'id': '1',
        'imgUrl': 'https://ss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=2593844834,2702597776&fm=58&bpow=800&bpoh=575',
        'title': '大连圣亚海洋世界',
        'desc': '浪漫大连首站，浪漫的海洋主题乐园'
      },
      {
        'id': '2',
        'imgUrl': 'https://ss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=2593844834,2702597776&fm=58&bpow=800&bpoh=575',
        'title': '大连圣亚海洋世界',
        'desc': '浪漫大连首站，浪漫的海洋主题乐园'
      },
      {
        'id': '3',
        'imgUrl': 'https://ss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=2593844834,2702597776&fm=58&bpow=800&bpoh=575',
        'title': '大连圣亚海洋世界',
        'desc': '浪漫大连首站，浪漫的海洋主题乐园'
      }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl';
  .recommend-title
    font-size :.3rem
    margin-top .2rem
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
