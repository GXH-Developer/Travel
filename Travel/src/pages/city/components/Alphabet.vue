<template>
  <ul class="list">
    <li class="item" v-for=" item of letters" :key="item"
    @click="handleLetterClick"
    @touchstart="handleTouchStart"
    @touchmove="handleTouchMove"
    @touchend="handleTouchEnd"
    :ref="item">{{item}}</li>
  </ul>
</template>

<script>
export default {
  name: 'Alphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatues: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatues = true
    },
    handleTouchMove (e) {
      if (this.touchStatues) {
        if (this.timer) {
          clearTimeout(this.timer)
        } else {
          const startY = this.startY
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - startY) / 20)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }
      }
    },
    handleTouchEnd () {
      this.touchStatues = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibales.styl';
  .list
    display :flex
    flex-direction :column
    justify-content :center
    position :absolute
    right :0
    bottom :0
    top :1.58rem
    width :.4rem
    .item
      line-height :.4rem
      text-align :center
      color :$color-bg
      font-size :.15rem
</style>
