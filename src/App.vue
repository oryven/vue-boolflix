<template>
  <div id="app">
    <Myheader @sceltaFilm="cambioFilm"/>
    <MyMain :elencoFilm="elencoFilm"/>
  </div>
</template>

<script>
import Myheader from './components/Myheader.vue'
import MyMain from '@/components/MyMain.vue'
import axios from "axios"

export default {
  name: 'App',
  components: {
    Myheader,
    MyMain
  },
  data(){
    return {
      titFilm: "",
      apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=9be0976a76aebe54d69d16966b3bea75&query=marvel",
      elencoFilm: []
    }
  },

   created(){
    this.schedaFilm()
  },

  methods: {
      cambioFilm(film) {
      this.titFilm = film;
    },

    schedaFilm(){
      axios
        .get(this.apiUrl + this.titFilm)
        .then((result) => {
        this.elencoFilm = result.data.results
        console.log(result);
      })
    }
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
