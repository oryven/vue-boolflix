<template>
  <div id="app">
    <Myheader @sceltaFilm="cambioFilm"/>
    <MyMain :elencoFilm='elencoFilm' :elencoSerie="elencoSerie"/>
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
      titoloFilm: "",
      query: "&query=",
      lingua: "&language=it-IT",
      apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=9be0976a76aebe54d69d16966b3bea75",
      elencoFilm: [],
      apiSerie:"https://api.themoviedb.org/3/search/tv?api_key=9be0976a76aebe54d69d16966b3bea75",
      elencoSerie:[]
    }
  },

  methods: {
      cambioFilm(film) {
      this.titoloFilm = film;

      axios
      .get(this.apiUrl + this.lingua + this.query + this.titoloFilm )
      .then((result) => {
      this.elencoFilm = result.data.results
      console.log(result);
      })

      axios
      .get(this.apiSerie + this.lingua + this.query + this.titoloFilm)
      .then((result) => {
      this.elencoSerie = result.data.results
      console.log(result);
      })
    },  

  }
  
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
