<template>
  <main class="bg-secondary py-5">
    <div class="container">
      <div class="row row-cols-2 row-cols-md-5 g-3 d-flex flex-wrap">
        <AlbumDischi
          v-for="album in filterArray" :key="album.title"
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
  props: {
    arrDischi: Array,
    genereSelezionato: String,
    autoreSelezionato: String
  },
  components: {
    AlbumDischi
  },
  computed: {
    filterArray () {
      return this.arrDischi.filter(obj => obj.genre.includes(this.genereSelezionato) && obj.author.includes(this.autoreSelezionato))
    }
  }
}
</script>

<style scoped lang="scss">
main {
  height: calc(100vh - 70px);
}
</style>
