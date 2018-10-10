<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="banner-title">{{this.singhtName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>
          {{this.bannerImgs.length}}
        </div>
      </div>
    </div>
    <fade-anmition>
      <common-gallary :imgs="bannerImgs" @close="handleGallaryClose" v-show="showGallary"></common-gallary>
    </fade-anmition>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnmition from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary,
    FadeAnmition
  },
  props: {
    singhtName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleGallaryClose () {
      this.showGallary = false
    },
    handleBannerClick () {
      this.showGallary = true
    }
  }
}
</script>
<style lang="stylus" scoped>
.banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      padding: 0 .4rem
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-tittle
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        position : absolute
        right: .4rem
        .banner-icon
          font-size: .24rem
</style>
