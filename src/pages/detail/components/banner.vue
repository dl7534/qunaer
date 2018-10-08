<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1507/e4/a3f526c57e0115798af52929d294ddd6.water.jpg_600x330_33fbf9b7.jpg" alt="">
      <div class="banner-info">
        <div class="banner-title">大连圣亚海洋世界(AAAA景区)</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>
          39
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" @close="handleGallaryClose" v-show="showGallary"></common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      imgs: [
        'http://img1.qunarzz.com/sight/p0/1507/e4/a3f526c57e0115798af52929d294ddd6.water.jpg_r_800x800_b0f6ec5d.jpg',
        'http://img1.qunarzz.com/sight/p0/1409/18/691791f00f29bce28a90f898d3faab1a.jpg_r_800x800_6f65375a.jpg',
        'http://img1.qunarzz.com/sight/p0/1409/18/a0657073c6e21e7dfbde415d19039c5a.jpg_r_800x800_682a02fc.jpg'
      ],
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
