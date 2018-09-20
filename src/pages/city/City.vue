<template>
  <div class="">
    <Header></Header>
    <Search></Search>
  </div>
</template>
<script>
import Header from './components/Header'
import Search from './components/Search'

export default {
  name: 'City',
  components: {
    Header,
    Search
  }
}
</script>
