<template>
    <div class="movie-wrapper" :style="styles">
        <div class="movie-info">
<h1>{{movie.title}}</h1>
<h3> Datede soritie : {{movie.release_date}}</h3>
<p>{{movie.overview}}</p>
</div>
    </div>
</template>

<script>
const BACKDROP_PATH = 'https://image.tmdb.org/t/p/w1280'
export default {
  data () {
    return {
      movie: {}
    }
  },
  beforeCreate () {
    console.log('before create')
  },
  created: function () {
    this.fetchData()
  },
  beforeMount () {
    console.log('before mount')
  },
  beforeUpdate () {
    console.log('before update')
  },
  computed: {
    styles () {
      return {
        background: `url(${BACKDROP_PATH}/${this.movie.backdrop_path}) no-repeat center center`

      }
    }
  },
  methods: {
    fetchData: async function () {
      try {
        const res = await fetch(
          `https://api.themoviedb.org/3/movie/${this.$route.params.id}?api_key=ba4cd8c90687bc55733de5607ea95d25`)
        const movie = await res.json()
        this.movie = movie
      } catch (e) {
        console.log(e)
      }
    }
  },
}
</script>

<style scoped>
.movie-wrapper{
    margin:auto;
    position: relative;
    padding-top: 45vh;
    background-size: cover;
}
.movie-info{
    background: #fff;
    color:#222;
    padding: 2rem 10%;
}
</style>
