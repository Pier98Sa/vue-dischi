<template>
  <div class="loader">
    <h1>
        Loading...
    </h1>
  </div>
</template>

<script>
export default {
    name:'PageLoad'

}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

.loader {
    position: fixed;
    left: 0;
    top: 0;
    width: 100vw;
    height: 100vh;
    background-color: $secondaryColor;
    display: flex;
    justify-content: center;
    align-items: center;
    
    h1 {
        font-size: 40px;
        color: $quaternaryColor;
    }
}

</style>