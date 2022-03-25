<template>
  <header class="bg-primary d-flex justify-content-between align-items-center">
    <img src="../assets/img/logo.png" alt="">
    <select @change="passValore" class="me-3" name="filter-album" id="filter-album">
      <option value="tutti">Tutti</option>
      <option v-for="(genere, index) in arrGenere" :key="index" :value="genere">{{ genere }}</option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'HeaderDischi',
  data () {
    return {
      opt: '',
      value: 'tutti'
    }
  },
  props: {
    arrGenere: Array
  },
  methods: {
    passValore () {
      this.opt = document.querySelector('select')
      this.value = this.opt.value
      this.$emit('passValue', this.value)
      console.log('header', this.value)
    }
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
