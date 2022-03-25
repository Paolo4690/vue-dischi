<template>
  <div class="col">
    <div class="p-3 bg-primary h-100">
      <img :src="image" class="w-100" :alt="titolo">
      <div class="cont-txt text-center">
        <h1 class="text-white fs-4">{{ autore }}</h1>
        <span class="d-block">{{ titolo }}</span>
        <span>{{ year }}</span>
        </div>
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
span {
    color: #8d8d8d;
}
</style>
