<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgurl" alt="">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        'id': '1',
        'imgurl': 'https://aecpm.alicdn.com/simba/img/TB1hQMzkmzqK1RjSZFHSuv3CpXa.jpg'
      },
      {
        'id': '2',
        'imgurl': 'https://img.alicdn.com/tfs/TB1zu9diYPpK1RjSZFFXXa5PpXa-520-280.jpg_q90_.webp'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper
  overflow: hidden
  width: 100%
.swiper-img
  width: 100%;
</style>
