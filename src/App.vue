<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
  </div>
</template>

<script>
import { getSeller } from 'api'
import VHeader from './components/v-header/v-header.vue'

export default {
  name: 'App',
  data() {
    return {
      seller: {}
    }
  },
  components: {
    VHeader
  },
  created() {
    this._getSeller()
  },
  methods: {
    _getSeller() {
      getSeller().then((seller) => {
        this.seller = seller
      })
    }
  }
}
</script>

<style lang="stylus">
// #app
//   font-family Avenir, Helvetica, Arial, sans-serif
//   -webkit-font-smoothing antialiased
//   -moz-osx-font-smoothing grayscale
//   text-align center
//   color #2c3e50
//   margin-top 60px
</style>
