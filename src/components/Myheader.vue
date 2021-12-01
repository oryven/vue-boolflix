<template>
  <header>
      <h1>BOOLFLIX</h1>
      <div>
        <input type="text" placeholder="Cerca un film"  v-model="testoUtente">
        <button @click="$emit('sceltaFilm', testoUtente)">Cerca</button>
      </div>
      
  </header>
</template>

<script>

export default {
  name: 'Myheader',
  props: {
    msg: String
  },
  data (){
    return {
        testoUtente: "",
    }   
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
    background-color: black;
    height: 80px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px 0 20px;
    h1 {
        color : red;
    }
    input {
        height: 30%;
    }
    button {
        height: 30%
    };
}
</style>
