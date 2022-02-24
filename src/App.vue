<template>
  <div id="app">
    <MyHeader :selezioni="arraygeneri" @genreSelected="genre"/>
    <MyMain @generi="generazioneSelect" :genere="genereSelezionato"/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'

export default {
  name: 'App',
  data (){
    return {
      arraygeneri:[],
      genereSelezionato:"Select genre",
    }
  },
  components: {
    MyHeader,
    MyMain,
    
  },
  methods:{
    generazioneSelect(generi){
      this.arraygeneri = generi;
      console.log(this.arraygeneri);
    },
    genre(select){
      this.genereSelezionato = select;
      console.log("mi trovo nel app e ho la select" + this.genereSelezionato);
    }
  }
}
</script>

<style lang="scss">
  @import './style/general.scss';

</style>
