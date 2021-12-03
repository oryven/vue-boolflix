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

      <img class="bandiera" :src="bandiera()">

      <font-awesome-icon icon="star" class="active" v-for="index in stars()" :key="index" />

      <p>{{details.overview}}</p>

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
      imgnetUrl:"https://i.pinimg.com/originals/a0/25/5d/a0255d73a758bf7b8eaf81e07e8f125d.jpg"
    }   
  },
methods:{
  bandiera(){
      if(this.details.original_language === 'it'){
        console.log('aaa');
        return "https://www.buy-spares.ie/sites/responsive/img/universal/flags/it-flag.png"
      }else if(this.details.original_language === 'en'){
        console.log('aaa');
        return "https://th.bing.com/th/id/R.8a8a985a6266b52f32e326ef17603955?rik=uoYiPLaWj9Yt0g&riu=http%3a%2f%2fwww.rgledhill.co.uk%2fimages%2fgb_flag.gif&ehk=IYDSLs30Co0xTYL1Zh9%2bhzwBPjI3S2IfGi5SQdjVkro%3d&risl=&pid=ImgRaw&r=0"
      }else {
        console.log('aaa');
        return "https://upload.wikimedia.org/wikipedia/commons/thumb/e/ef/International_Flag_of_Planet_Earth.svg/1280px-International_Flag_of_Planet_Earth.svg.png"
      }
    },

    stars() {
          return Math.floor((this.details.vote_average) / 2)
      }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .scheda-film {
    position: relative;
    width: calc(100% / 4 - 20px);
    height: 450px;
    margin: 20px 10px;
    color:white;
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
  .scheda-film:hover img:not(.bandiera) {
      display:none;
    }

  .scheda-film:hover .container-details{
    display:block;
  }

  .active {
    margin-bottom: 10px;
  color: yellow;
}

</style>