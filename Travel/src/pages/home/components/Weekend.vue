<template>
    <div>
        <div class="recommend-title">周末去哪</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
               <div class="item-img-wrapper">
                <img class="item-img" :src="item.imgUrl" alt="">
               </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        'id': '0',
        'imgUrl': 'https://gss2.bdstatic.com/9fo3dSag_xI4khGkpoWK1HF6hhy/baike/s%3D220/sign=2bd81c777aec54e745ec1d1c89399bfd/18d8bc3eb13533fa886c0267a9d3fd1f40345ba4.jpg',
        'title': '大连圣亚海洋世界',
        'desc': '浪漫大连首站，浪漫的海洋主题乐园'
      },
      {
        'id': '1',
        'imgUrl': 'https://gss2.bdstatic.com/9fo3dSag_xI4khGkpoWK1HF6hhy/baike/s%3D220/sign=2bd81c777aec54e745ec1d1c89399bfd/18d8bc3eb13533fa886c0267a9d3fd1f40345ba4.jpg',
        'title': '大连圣亚海洋世界',
        'desc': '浪漫大连首站，浪漫的海洋主题乐园'
      },
      {
        'id': '2',
        'imgUrl': 'https://gss2.bdstatic.com/9fo3dSag_xI4khGkpoWK1HF6hhy/baike/s%3D220/sign=2bd81c777aec54e745ec1d1c89399bfd/18d8bc3eb13533fa886c0267a9d3fd1f40345ba4.jpg',
        'title': '大连圣亚海洋世界',
        'desc': '浪漫大连首站，浪漫的海洋主题乐园'
      },
      {
        'id': '3',
        'imgUrl': 'https://gss2.bdstatic.com/9fo3dSag_xI4khGkpoWK1HF6hhy/baike/s%3D220/sign=2bd81c777aec54e745ec1d1c89399bfd/18d8bc3eb13533fa886c0267a9d3fd1f40345ba4.jpg',
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
   .item-img-wrapper
     overflow :hidden
     height :0
     padding-bottom :33.9%
     .item-img
       width :100%
   .item-info
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
</style>
