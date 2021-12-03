<template>
  <section>
    <div class="movies">
      <Film v-for="film, i in elencoFilm" 
      :key="i"
      :details="film"/>
    </div>

    <div class="series">
      <Serie v-for="serie, j in elencoSerie" 
      :key="j"
      :details="serie"/>
    </div>      
  </section>
</template>

<script>

import Film from '@/components/Film.vue'
import Serie from '@/components/Serie.vue'

export default {
  name: 'MyMain',
  components: {
    Film,
    Serie
  },
  props: {
   elencoFilm: Array,
   elencoSerie: Array
  },
  data (){
    return {
       
    }   
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section{

height: calc(100vh - 80px) ;
  background-color: #56050c;
  overflow-y: scroll;
.movies, .series {
  display: flex;
  flex-wrap:wrap ;
  }
}
</style>
