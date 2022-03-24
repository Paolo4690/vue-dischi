<template>
  <main class="bg-secondary py-5">
    <div class="container d-flex  justify-content-between flex-wrap">
        <AlbumDischi
          v-for="album in arrDischi" :key="album.title"
          :autore="album.author"
          :image="album.poster"
          :titolo="album.title"
          :year="album.year"
        />
    </div>
  </main>
</template>

<script>
import AlbumDischi from './AlbumDischi.vue'

export default {
  name: 'MainDischi',
  props: {
    arrDischi: Array
  },
  components: {
    AlbumDischi
  }
}
</script>

<style scoped lang="scss">

</style>
