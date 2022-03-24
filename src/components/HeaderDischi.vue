<template>
  <header class="bg-primary d-flex justify-content-between align-items-center">
    <img src="../assets/img/logo.png" alt="">
    <select class="me-3" name="filter-album" id="filter-album">
      <option value="tutti">Tutti</option>
      <option v-for="(genere, index) in arrGenere" :key="index" :value="index">{{ genere }}</option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'HeaderDischi',
  props: {
    arrGenere: Array
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
