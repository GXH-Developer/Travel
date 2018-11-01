<template>
  <div>
    <div class="banner" @click="handleGallaryClick">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="banner-title">
          {{sightName}}
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe790;</span>39
        </div>
      </div>
    </div>
    <fade-animation>
      <gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></gallary>
    </fade-animation>
  </div>
</template>

<script>
import Gallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/Fade'
export default {
  name: 'Banner',
  props: {
    imgs: Array,
    bannerImg: String,
    sightName: String
  },
  components: {
    Gallary,
    FadeAnimation
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleGallaryClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position :relative
    overflow :hidden
    height :0
    padding-bottom :55%
    .banner-img
      width :100%
      background-image :linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
    .banner-info
      display :flex
      position :absolute
      left :0
      right :0
      bottom :0
      line-height :.6rem
      color :#fff
      .banner-title
        flex :1
        font-size :.32rem
        padding :0 .2rem
      .banner-number
        height :.32rem
        line-height :.32rem
        margin-top :.14rem
        padding :0 .4rem
        border-radius :.2rem
        background :rgba( 0, 0, 0, .8)
        font-size :.24rem
        .banner-icon
          font-size :.24rem
</style>
