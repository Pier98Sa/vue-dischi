<template>
  <div id="app">
    <MyHeader @Generi ="generazioneSelect"/>
    <MyMain />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain,
    
  },
  methods:{
    generazioneSelect(){
      
    }
  }
}
</script>

<style lang="scss">
  @import './style/general.scss';

</style>
