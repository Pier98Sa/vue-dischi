<template>
    
    <div class="box d-flex flex-column ">
        <div class="cover p-3">
            <img class="img-fluid" :src="album.poster">
        </div>

        <div class="cover-text text-center p-2 d-flex flex-column justify-content-between">
            <h2 class="text-white text-uppercase fs-4 p-3">{{album.title}}</h2>
            <div class="singer-year">
                <h3 class="ms_color-text fs-6">{{album.author}}</h3>
                <h3 class="ms_color-text fs-6">{{album.year}}</h3>
            </div>
            
        </div>
        
    </div>
    
    
  
</template>

<script>
export default {
    name: 'CoverAlbum',
    props:{
        "album": Object,
    }
}
</script>

<style lang="scss" scoped>

@import '../../style/variables.scss';

.box{
    height: 100%;
    background-color: $primaryColor;


    .ms_color-text{
        color: $tertiaryColor;
    }
        
}
</style>