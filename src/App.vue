<template>
  <div id="app">
    <Header
    :title="title"/>
    <transition name="fade">
        <router-view />
    </transition>

  </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'App',
  data () {
    return {
      hello: 'Hello World',
      title: 'Movie Vue DB'
    }
  },
  components: {
    Header
  }
}
</script>

<style >

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
}
.fade-enter-active, .fade-leave-active{
    transition: all 0.6s ease;
}
.fade-enter, .fade-leave-to{
    opacity: 0;
    transform: transform(100);
}
</style>
