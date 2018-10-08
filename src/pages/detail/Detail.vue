<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>
<script>
import DetailBanner from './components/banner'
import DetailHeader from './components/header'
import DetailList from './components/list'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [{
        title: '成人票',
        children: [{
          title: '成人三联馆票',
          children: [{
            title: '大润发超市'
          }]
        }, {
          title: '成人四联馆票'
        }]
      }, {
        title: '儿童票'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
.content
  height: 50rem
</style>
