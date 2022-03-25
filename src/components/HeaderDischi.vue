<template>
  <header class="bg-primary d-flex justify-content-between align-items-center">
    <img src="../assets/img/logo.png" alt="">
    <div class="cont-select me-3">
      <label for="filter-author" class="text-white fs-5 pe-2">Filtra per Cantante</label>
      <select v-model="valAutore" @change="$emit('passAutore', valAutore)" name="filter-author" id="filter-author">
        <option value="tutti">Tutti</option>
        <option v-for="autore in arrAutore" :key="autore" :value="autore">{{ autore }}</option>
      </select>
    </div>
    <div class="cont-select me-3">
      <label for="filter-genere" class="text-white fs-5 pe-2">Filtra per genere musicale</label>
      <select v-model="valGenere" @change="$emit('passValue', valGenere)" name="filter-genere" id="filter-genere">
        <option value="tutti">Tutti</option>
        <option v-for="genere in arrGenere" :key="genere" :value="genere">{{ genere }}</option>
      </select>
    </div>
  </header>
</template>

<script>
/* eslint-disable */
export default {
  name: 'HeaderDischi',
  data () {
    return {
      valGenere: '',
      valAutore: ''
    }
  },
  props: {
    arrGenere: Array,
    arrAutore: Array
  }
}
</script>

<style scoped lang="scss">
header {
  height: 70px;
  img {
    width: 50px;
  }
}
</style>
