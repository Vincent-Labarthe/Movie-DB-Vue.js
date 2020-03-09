<template>
<header>
      <h1><router-link to="/">
      <img src="../assets/logo.svg">
      </router-link></h1>
</header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: String
  },
  data () {
    return {
      show: false
    }
  }
}
</script>

<style scoped>
header{
    background-color: #111;
    padding:20px;
    color:white;
}
h1{
    margin: 0;
}
img{
  width: 5rem;
}

/* name-enter -> name-enter-to */
/* name-enter-active */

/* name-leave -> name-leave-to */
/* name-leave-active */
</style>
