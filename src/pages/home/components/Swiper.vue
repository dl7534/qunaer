<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
    <swiper-slide v-for='item of swiperList' :key="item.id">
      <img class='swiper-img' :src="item.imgUrl">
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
        pagination: {
          el: '.swiper-pagination'
        },
        loop: true
      },
      swiperList: [{
        id: '1001',
        imgUrl: 'https://img1.qunarzz.com/order/comp/1805/2e/6e407f088bfb902.png'
      },
      {
        id: '1002',
        imgUrl: 'https://img1.qunarzz.com/qs/1809/f6/18a4edd3d78d1102.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 24.25%
    background: #eee
    .swiper-img
      width: 100%
</style>
