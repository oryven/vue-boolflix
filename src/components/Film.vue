<template>

      <div class="scheda-film">
        <h2>Film</h2>
        <div>{{details.name}}</div>

        <img :src="ImgUrl + details.poster_path">
        
        <div>{{details.original_title}}</div>

        <img :src="bandiera()">

        <div>{{details.vote_average}}</div>
      </div>
    
</template>

<script>

export default {
  name: 'Film',
  props: {
   details: Object
  },
  data (){
    return {
      ImgUrl: "https://image.tmdb.org/t/p/w185"
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
  .scheda-film {
    text-align: center;
    border: 1px solid black;
    width: calc(100% / 5 - 10px);
    margin: 20px 5px;
  }

</style>