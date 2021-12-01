<template>
  <section>

  </section>
</template>

<script>
// import axios from "axios";

export default {
  name: 'MyMain',
  props: {
   titFilm: String
  },
  data (){
    return {
        // testoUtente: "",
        // apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=9be0976a76aebe54d69d16966b3bea75&query=",
        // elencoFilm: []
    }   
  },

  // created(){
  //   this.schedaFilm()
  // },
  // methods: {
  //     schedaFilm(){
  //         axios
  //         .get(this.apiUrl + this.titFilm)
  //         .then((result) => {
  //             this.elencoFilm = result.data.results
  //             console.log(result);
  //         })
  //       }
  //   }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section{
    background-color: lightgray;
    height: 100vh;
}

</style>
