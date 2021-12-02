<template>
  <section>

      <div class="scheda-film">
        <h2>Film</h2>
        <div>{{details.title}}</div>
        
        <div>{{details.original_title}}</div>

        <img :src="bandiera()">

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
methods:{
  bandiera(){
      if(this.details.original_language === 'it'){
        return "https://www.buy-spares.ie/sites/responsive/img/universal/flags/it-flag.png"
      }else if(this.details.original_language === 'en'){
        return "https://th.bing.com/th/id/R.8a8a985a6266b52f32e326ef17603955?rik=uoYiPLaWj9Yt0g&riu=http%3a%2f%2fwww.rgledhill.co.uk%2fimages%2fgb_flag.gif&ehk=IYDSLs30Co0xTYL1Zh9%2bhzwBPjI3S2IfGi5SQdjVkro%3d&risl=&pid=ImgRaw&r=0"
      }
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section {
    height: 50px;
    .scheda-film {
      border: 1px solid black;
    }
}

</style>