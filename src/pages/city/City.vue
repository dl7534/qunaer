<template>
  <div class="">
    <Header></Header>
    <Search></Search>
    <List :letters="letters" :cities="cities" :hot="hotCities"></List>
    <city-alphabet :cities="cities" @change="handleLetterChange"></city-alphabet>
  </div>
</template>
<script>
import axios from 'axios'
import Header from './components/Header'
import Search from './components/Search'
import List from './components/List'
import CityAlphabet from './components/Alphabet'

export default {
  name: 'City',
  data () {
    return {
      cities: {},
      hotCities: [],
      letters: ''
    }
  },
  components: {
    Header,
    Search,
    List,
    CityAlphabet
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(this.handleGetCityInfoSucc)
    },
    handleGetCityInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    handleLetterChange (letter) {
      this.letters = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>
