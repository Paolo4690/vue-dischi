<template>
  <div id="app">
    <header-dischi
      :arrGenere= arrGenere
    />
    <main-dischi-Empty v-if="arrDischi == null" />
    <main-dischi v-else
      :arrDischi= arrDischi
    />
  </div>
</template>

<script>
import HeaderDischi from './components/HeaderDischi.vue'
import MainDischi from './components/MainDischi.vue'
import MainDischiEmpty from './components/MainDischiEmpty.vue'

import axios from 'axios'

export default {
  name: 'App',
  components: {
    HeaderDischi,
    MainDischi,
    MainDischiEmpty
  },
  data () {
    return {
      arrDischiEmpty: '',
      arrDischi: null,
      arrGenere: null
    }
  },
  created () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((risposta) => {
        this.arrDischi = risposta.data.response
      })
  }
}
</script>

<style lang="scss">
$primary: #2e3a46;
$secondary: #1e2d3b;
@import '~bootstrap/scss/bootstrap';
@import './assets/styles/style';

</style>
