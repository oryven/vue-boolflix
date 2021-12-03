<template>
  <div class="scheda-serie">
    <div class="copertina">
      <img class="logo-netflix" v-if="details.poster_path === null" :src="imgnetUrl" alt="">

      <img v-else :src="ImgUrl + details.poster_path">
    </div>
    <div class="container-details">
      <h2>Serie</h2>

      <div>{{details.name}}</div>
        
      <div>{{details.original_title}}</div>

      <img class="bandiera" :src="bandiera()">

      <font-awesome-icon icon="star" class="active" v-for="index in 5" :key="index" />

      <p>{{details.overview}}</p>

      <div>{{details.vote_average / 2}}</div>
    </div>   
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
      ImgUrl: "https://image.tmdb.org/t/p/w300",
      imgnetUrl:"https://i.pinimg.com/originals/a0/25/5d/a0255d73a758bf7b8eaf81e07e8f125d.jpg"
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
.scheda-serie {
    position: relative;
    width: calc(100% / 4 - 10px);
    margin: 20px 5px;
    color: white;
    height:450px;
     .container-details {
      display: none;
      padding: 10px;
      width: 100%;
      height: 100%;
      overflow-y:scroll;
      background-color: rgba($color: #000000, $alpha: 0.5);
      // p {
       
      // }
    }
    .copertina {
      position: absolute;
      width: 100%;
      height: 100%;
    }
    .bandiera {
      margin: 10px 0;
      width: 30px;
      display: block;
    }
    .logo-netflix{
        width: 100%;
        height: 100%;
    }
  }
  .scheda-serie:hover img:not(.bandiera){
      display:none;
    }

  .scheda-serie:hover .container-details{
    display:block;
  }

.active {
  color: yellow;
  margin-bottom: 10px;
}
</style>