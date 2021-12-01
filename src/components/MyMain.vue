<template>

  <div class="movies">
    <Film v-for="film, i in elencoFilm" 
    :key="i"
    :details="film"/>
  </div>
    
</template>

<script>

import Film from '@/components/Film.vue'
export default {
  name: 'MyMain',
  components: {
    Film
  },
  props: {
   elencoFilm: Array
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
