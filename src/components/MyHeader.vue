<template>
  <header class="d-flex align-items-center justify-content-between">
    <img class="img-fluid p-2" alt="spotify logo" src="../assets/Spotify_Logo.png">
    
    <select class="form-select me-2 ms_input" name="genresSelect" id="Album-Select" 
    v-model="selected" @change="$emit('genreSelected',selected)">
      <option value="">Select genre </option>
      <option v-for="(selezione, index) in selezioni" :key = index :value="selezione">
        {{selezione}}
      </option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'MyHeader',
  props: {
    selezioni : Array
  },
  data(){
    return{
      selected:"",
    }
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import '../style/variables.scss';

  header{
    background-color: $primaryColor;
    height: 100px;

    img{
      height: 80px;
    }

    
  }

  .ms_input{
    width: 200px;
  }

</style>
