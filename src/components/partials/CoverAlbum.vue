<template>
    
    <div class="box d-flex flex-column ">
        <div class="cover p-3">
            <img class="img-fluid" :src="album.poster">
        </div>

        <div class="cover-text text-center p-2">
            <h2 class="text-white text-uppercase fs-4 p-3">{{album.title}}</h2>
            <div class="ms_color-text">{{album.author}}</div>
            <div class="ms_color-text">{{album.year}}</div>
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

    .cover{
        height: 50%;
    }

    .cover-text{
        height: 50%;
    }

    .ms_color-text{
        color: $tertiaryColor;
    }
        
}
</style>