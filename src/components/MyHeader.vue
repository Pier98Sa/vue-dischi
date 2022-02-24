<template>
  <header class="d-flex align-items-center justify-content-between">
    <img class="img-fluid p-2" alt="spotify logo" src="../assets/Spotify_Logo.png">
    <select class="form-select me-2 ms_w-15" name="genresSelect" id="Album-Select">

    </select>
  </header>
</template>

<script>
export default {
  name: 'MyHeader',
  
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

  .ms_w-15{
    width: 15%;;
  }

</style>
