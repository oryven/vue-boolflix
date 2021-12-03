<template>

  <div class="scheda-film">
        
    <div class="copertina">
      <img class="logo-netflix" v-if="details.poster_path === null" :src="imgnetUrl" alt="">
      <img v-else :src="ImgUrl + details.poster_path">
    </div>

    <div class="container-details">
      <h2>Film</h2>

      <div>{{details.name}}</div>
        
      <div>{{details.original_title}}</div>

      <div>{{details.overview}}</div>

      <img class="bandiera" :src="bandiera()">

      <div>{{details.vote_average}}</div>
    </div>   
    
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
      ImgUrl: "https://image.tmdb.org/t/p/w300",
      imgnetUrl:"https://www.losbagliato.it/wp-content/uploads/2021/07/copertina-netflix-23-giugno-960x960.png"
    }   
  },
methods:{
  bandiera(){
      if(this.details.original_language === 'it'){
        return "https://www.buy-spares.ie/sites/responsive/img/universal/flags/it-flag.png"
      }else if(this.details.original_language === 'en'){
        return "https://th.bing.com/th/id/R.8a8a985a6266b52f32e326ef17603955?rik=uoYiPLaWj9Yt0g&riu=http%3a%2f%2fwww.rgledhill.co.uk%2fimages%2fgb_flag.gif&ehk=IYDSLs30Co0xTYL1Zh9%2bhzwBPjI3S2IfGi5SQdjVkro%3d&risl=&pid=ImgRaw&r=0"
      }else 
        return "https://upload.wikimedia.org/wikipedia/commons/thumb/e/ef/International_Flag_of_Planet_Earth.svg/1280px-International_Flag_of_Planet_Earth.svg.png"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .scheda-film {
    position: relative;
    width: calc(100% / 4 - 10px);
    height: 450px;
    margin: 20px 5px;
    color: #e50913;
    .container-details {
      padding: 10px;
      width: 100%;
      height: 100%;
      overflow-y:scroll;
    }
    .copertina {
      position: absolute;
      width: 100%;
      height: 100%;
    }
    .bandiera {
      width: 30px;
    }
    .logo-netflix{
        width: 185px;
        // height: 272px;
    }
  }
  .scheda-film:hover img{
      display:none;
    }

</style>