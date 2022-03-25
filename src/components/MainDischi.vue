<template>
  <main class="bg-secondary py-5">
    <div class="container">
      <div class="row row-cols-2 row-cols-md-5 g-3 d-flex flex-wrap">
        <AlbumDischi
          v-for="album in filterArray()" :key="album.title"
          :autore="album.author"
          :image="album.poster"
          :titolo="album.title"
          :year="album.year"
        />
      </div>
    </div>
  </main>
</template>

<script>
import AlbumDischi from './AlbumDischi.vue'

export default {
  name: 'MainDischi',
  data () {
    return {
      arrFilteredGenere: []
    }
  },
  props: {
    arrDischi: Array,
    valoreSelezionato: String
  },
  components: {
    AlbumDischi
  },
  methods: {
    filterArray () {
      console.log()
      if (this.valoreSelezionato === 'tutti') {
        return this.arrDischi
      } else {
        return this.arrDischi.filter((obj) => obj.genre.includes(this.valoreSelezionato))
      }
    }
  }
}
</script>

<style scoped lang="scss">

</style>
