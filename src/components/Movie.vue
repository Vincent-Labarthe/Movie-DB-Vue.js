<template>
<router-link :to="moviePath"><img :src="completUrl" :alt="movie.title" /></router-link>
</template>

<script>
const POSTER_PATH = 'https://image.tmdb.org/t/p/w154'
export default {
  props: ['movie'],
  computed: {
    completUrl: function () {
      return `${POSTER_PATH}/${this.movie.poster_path}`
    },
    moviePath: function () {
      return `/movie/${this.movie.id}`
    }
  }
}
</script>

<style scoped>
img {
    box-shadow: 0 0 035px black;
}
</style>
