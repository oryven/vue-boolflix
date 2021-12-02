<template>
  <section>
    <div class="movies">
      <Film v-for="film, i in elencoFilm" 
      :key="film+i"
      :details="film"/>
    </div>

    <div>
      <Serie v-for="serie, i in elencoSerie" 
      :key="serie+i"
      :details="film"/>
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
.movies {
  display: flex;
  flex-wrap:wrap ;
  height: 100vh;
  background-color: lightgray;
  }

</style>
