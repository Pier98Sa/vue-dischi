<template>
  <main>
    <div class="container py-5">
      <div class="row row-cols-5 ">
        <div class="col g-4" v-for="(album, index) in listaAlbum" :key="index">
          <CoverAlbum :album="album"/>
        </div>
        

      </div>

    </div>

  </main>
</template>

<script>

const axios = require('axios');

import CoverAlbum from './partials/CoverAlbum.vue'

export default {
  name: 'MyMain',
  data(){
    return{
      listaAlbum: [],
      api: "https://flynn.boolean.careers/exercises/api/array/music"
    }
  },
  components:{
    CoverAlbum,
  },
  methods:{
    getAlbum(){
      axios.get(this.api)
      .then((response) => {
        this.listaAlbum = response.data.response;
        console.log(this.listaAlbum);
      });
    }
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
