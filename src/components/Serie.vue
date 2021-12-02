<template>
  <section>

      <div class="scheda-serie">

        <div>{{details.title}}</div>
        
        <div>{{details.original_title}}</div>

        <div>{{details.original_language}}</div>

        <div>{{details.vote_average}}</div>
      </div>
    
  </section>
</template>

<script>

export default {
  name: 'Film',
  props: {
   details: Object
  },
  data (){
    return {
       
    }   
  },


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section {
    height: 50px;
}

</style>