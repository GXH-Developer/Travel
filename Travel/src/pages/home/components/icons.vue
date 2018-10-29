<template>
  <div class="icons">
    <swiper :options="swiperOption">
        <swiper-slide v-for="(page,index) of pages" :key="index">
            <div class="icon" v-for="item of page" :key="item.id">
                <div class="icon-img">
                    <img class="icon-img-contain" :src="item.imgUrl" alt="">
                </div>
                <p class="title">{{item.title}}</p>
            </div>
        </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'icons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibales.styl'
@import '~styles/mixins.styl'
  .icons
    margin-top :.2rem
    overflow :hidden
    height : 0
    padding-bottom :50%
    .icon
      position :relative
      float :left
      width :25%
      height :0
      padding-bottom :25%
      .icon-img
        position :absolute
        left :0
        top :0
        right :0
        bottom :.44rem
        box-sizing border-box
        padding :.1rem
        .icon-img-contain
          height :100%
          display :block
          margin :0 auto
    .title
      position :absolute
      bottom :0
      left :0
      right :0
      text-align :center
      line-height :.44rem
      height :.44rem
      font-size :.3rem
      color :dark-text-color
      ellipsis()
</style>
