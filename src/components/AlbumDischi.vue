<template>
  <div class="block bg-primary p-3 mb-3">
    <img :src="image" class="w-100" :alt="titolo">
    <div class="cont-txt text-center">
      <h1 class="fs-4">{{ autore }}</h1>
      <span class="d-block">{{ titolo }}</span>
      <span>{{ year }}</span>
      </div>
  </div>
</template>

<script>
export default {
  name: 'AlbumDischi',
  props: {
    autore: String,
    image: String,
    titolo: String,
    year: String
  }
}
</script>

<style scoped lang="scss">
.block {
  width: calc(100% / 5 - .8rem);
}
</style>
