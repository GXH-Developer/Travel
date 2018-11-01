<template>
  <div class="content">
    <detail-header></detail-header>
    <benner :sightName="sightName" :imgs="imgs" :bannerImg="bannerImg"></benner>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Benner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
export default {
  name: 'Detail',
  components: {
    Benner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [],
      sightName: '',
      imgs: [],
      bannerImg: ''
    }
  },
  methods: {
    getDetaiolInfo (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.list = data.categoryList
        this.imgs = data.gallaryImgs
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
      }
    }
  },
  activated () {
    axios.get('/static/mock/detail.json')
      .then(this.getDetaiolInfo)
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height :50rem
</style>
