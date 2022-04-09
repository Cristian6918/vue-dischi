<template>
<div class="container-fluid ct-header">
    <div class="logo">
        <img src="@/assets/spotify-logo.svg" alt="">
    </div>
</div>

</template>

<script>
export default {
    name:'HeaderComponent'

}
</script>

<style lang="scss" scoped>
@import '@/style/variables.scss';



.ct-header{
    height: 10vh;
    width:100%;
    background-color: $secondary-color;
}
.logo{
    position:absolute;
    width:50px;
    aspect-ratio: 1;
    padding:0;
    left:20px;
    top:20px;
  

    img{
        width:100%;
    }
}


</style>