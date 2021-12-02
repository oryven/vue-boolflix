<template>
    <div class="scheda-serie">
        <h2>Serie</h2>
        
        <img class="logo-netflix" v-if="details.poster_path === null" :src="imgnetUrl" alt="">

        <img v-else :src="ImgUrl + details.poster_path">

        <div>{{details.name}}</div>
        
        <div>{{details.original_title}}</div>

        <img :src="bandiera()">

        <div>{{details.vote_average}}</div>
    </div>
</template>

<script>

export default {
  name: 'Serie',
  props: {
   details: Object
  },
  data (){
    return {
       ImgUrl: "https://image.tmdb.org/t/p/w185",
      imgnetUrl:"https://www.losbagliato.it/wp-content/uploads/2021/07/copertina-netflix-23-giugno-960x960.png"
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
.scheda-serie {
    text-align: center;
    border: 1px solid black;
    width: calc(100% / 6 - 10px);
    margin: 20px 5px;
    background: black;
    color: #e50913;
    .logo-netflix{
        width: 185px;
        // height: 272px;
    }
  }

</style>