<template>
  <div id="app">
    <Myheader />
    <Main/>
  </div>
</template>

<script>
import Myheader from './components/Myheader.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Myheader,
    Main
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
