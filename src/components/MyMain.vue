<template>
  <main>
    <div class="container py-5">
      <div class="row row-cols-xl-5 row-cols-lg-4 row-cols-md-3 row-cols-sm-2 ">
        <div class="col g-4" v-for="(album, index) in listaAlbumFiltrati" :key="index">
          <CoverAlbum :album="album"/>
        </div>
        

      </div>

    </div>

    <PageLoad v-if="loadingInProgress"/>
  </main>
</template>

<script>

const axios = require('axios');

import CoverAlbum from './partials/CoverAlbum.vue'
import PageLoad from './PageLoad.vue'

export default {
  name: 'MyMain',
  props:{
    genere: String,
  },
  data(){
    return{
      listaAlbum: [],
      listaGeneri: [],
      loadingInProgress: true,
      api: "https://flynn.boolean.careers/exercises/api/array/music"
    }
  },
  components:{
    CoverAlbum,
    PageLoad
  },
  computed: {
    listaAlbumFiltrati(){
      if(this.genere == ""){
        return this.listaAlbum;
      }else {
        return this.listaAlbum.filter((elemento) =>{
          return elemento.genre == this.genere; 
        });
      } 
   },
  },

  methods:{
    getAlbum(){
      axios.get(this.api)
      .then((response) => {
        //popolamento dell'array listaAlbum
        this.listaAlbum = response.data.response;
        this.loadingInProgress = false;
        //popolamento dell'array listaGeneri
        this.listaAlbum.forEach((album) => {
          if(!this.listaGeneri.includes(album.genre)){
            this.listaGeneri.push(album.genre);
          }
        });

        this.$emit('generi',this.listaGeneri)
      });
    },

    
      
   
  },
  created(){
    this.getAlbum();
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/variables.scss';
  main{
    background-color: $secondaryColor;
    height: calc(100vh - 100px);
    overflow-y: auto;
  }


</style>
