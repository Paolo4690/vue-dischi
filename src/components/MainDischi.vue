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
import axios from 'axios'

export default {
  name: 'MainDischi',
  components: {
    AlbumDischi
  },
  data () {
    return {
      arrDischi: null
    }
  },
  created () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((risposta) => {
        this.arrDischi = risposta.data.response
        console.log(this.arrDischi)
      })
  }
}
</script>

<style scoped lang="scss">

</style>
