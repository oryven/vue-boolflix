<template>
  <section>
    <div>{{details.title}}</div>

    <div>{{details.original_title}}</div>

    <div>{{details.original_language}}</div>

    <div>{{details.vote_average}}</div>
  </section>
</template>

<script>

export default {
  name: 'Film',
  props: {
   film: Object
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
    background-color: lightgray;
    height: 100vh;
}

</style>