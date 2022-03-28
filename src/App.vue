<template>
  <div id="app">
    <header-dischi
      @passValue="selectGenere"
      @passAutore="selectAutore"
      :arrGenere= arrGenere
      :arrAutore= arrAutore
    />
    <main-dischi-Empty v-if="arrDischi == null" />
    <main-dischi v-else
      :arrDischi= arrDischi
      :genereSelezionato= genereSelezionato
      :autoreSelezionato= autoreSelezionato
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
      arrDischi: null,
      arrGenere: [],
      arrAutore: [],
      genereSelezionato: '',
      autoreSelezionato: ''
    }
  },
  methods: {
    selectGenere (optSelectGenere) {
      this.genereSelezionato = optSelectGenere
      if (this.genereSelezionato === 'tutti') {
        this.genereSelezionato = ''
      }
    },
    selectAutore (optSelectAutore) {
      this.autoreSelezionato = optSelectAutore
      if (this.autoreSelezionato === 'tutti') {
        this.autoreSelezionato = ''
      }
    }
  },
  created () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        this.arrDischi = response.data.response
        this.arrGenere = [...new Set(this.arrDischi.map(elemento => elemento.genre))]
        this.arrAutore = [...new Set(this.arrDischi.map(elemento => elemento.author))]
      })
  }
}
</script>

<style lang="scss">
$primary: #2e3a46;
$secondary: #1e2d3b;
@import '~bootstrap/scss/bootstrap';

</style>
