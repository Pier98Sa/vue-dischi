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
      genereSelezionato:"",
    }
  },
  components: {
    MyHeader,
    MyMain,
    
  },
  methods:{
    generazioneSelect(generi){
      this.arraygeneri = generi;
    },
    genre(select){
      this.genereSelezionato = select;
    }
  }
}
</script>

<style lang="scss">
  @import './style/general.scss';

</style>
