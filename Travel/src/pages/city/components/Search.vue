<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或者拼音"/>
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for="(item,index) of list" :key="index"
        @click="handleCityClick(item.name)">{{item.name}}</li>
         <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: []
    }
  },
  mounted () {
    this.scorll = new Bscroll(this.$refs.search)
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
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
  .search-content
    z-index :1
    overflow :hidden
    position :absolute
    background :#eee
    top :1.58rem
    left :0
    right :0
    bottom :0
    .search-item
      line-height :.62rem
      padding-left :.2rem
      font-size :.2rem
      color :#666
      background :#fff
</style>
