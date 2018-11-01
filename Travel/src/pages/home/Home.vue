<template>
    <div>
        <home-header></home-header>
        <home-swiper :swiperList="swiperList"></home-swiper>
        <home-icons :list="iconList"></home-icons>
        <home-recommend :recommendList="recommendList"></home-recommend>
        <home-weekend :weekendList="weekendList"></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/header'
import HomeSwiper from './components/swiper'
import HomeIcons from './components/icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
import { mapState } from 'vuex'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      swiperList: [],
      recommendList: [],
      weekendList: [],
      iconList: [],
      lastCity: ''
    }
  },
  mounted () {
    this.lastCity = this.city
    this.getHomeIfo()
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    getHomeIfo () {
      axios.get('/static/mock/index.json?city=' + this.city)
        .then(this.getHomeInfoSource)
    },
    getHomeInfoSource (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
        this.iconList = data.iconList
      }
    }
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeIfo()
    }
  }
}
</script>

<style>

</style>
